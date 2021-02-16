---
description: A tutorial on how to create custom Vehicles for your server
---

# Creating Custom Vehicles

{% hint style="warning" %}
Please visit our [legacy wiki](https://github.com/VolmitSoftware/VehiclesPlus/wiki) to begin creating new vehicles
{% endhint %}

## Create a new Class that extends Part, Colorable, Seat or ControllingSeat

* Part will create a new plain part type
* Colorable will create a colorable part type
* Seat will create a new empty seat
* ControllingSeat will create a new seat that listens to input

The Class should look like this \(This is the Turret part\)

```text
// This annotation will tell the serializer to include this class in saving
@IncludeInSerialize
public class Turret extends Colorable {
    // This annotation will tell the serializer to include this variable in saving
    @VPSerializable
    private Integer rotationOffset;
    @VPSerializable
    private Float explosionSize;
    @VPSerializable
    private ItemStack ammo;

    transient private Integer cooldown = 0;

    @Override
    public void spawnStand(Location base, SpawnedVehicle owningVehicle) {
        super.setOwningVehicle(owningVehicle);
        super.setHolder(new CustomArmorStand(base, super.getXOffset(), super.getYOffset(), super.getZOffset())
                .setGravity(false).setVisible(false).setInvulnerable(true).withName("VPPART")
                .setHelmet(getSkinColored()).getArmorStand());
        super.getHolder().setMetadata(NBTDataType.PART_DATA.name(), new FixedMetadataValue(Main.getInstance(), this));
    }

    public Turret(Double xOffset, Double yOffset, Double zOffset, Color color, ItemStack skin, Float explosionSize, ItemStack ammo) {
        super(xOffset, yOffset, zOffset, color, skin);
        this.explosionSize = explosionSize;
        this.ammo = ammo;
    }

    @Override
    public Location applyExtraOffset(Location loc) {
        loc.setYaw(loc.getYaw() + rotationOffset);
        return loc;
    }

    public CompletableFuture<Boolean> shoot() {
        CompletableFuture<Boolean> future = new CompletableFuture<>();
        new BukkitRunnable() {
            @Override
            public void run() {
                if (cooldown == 0) {
                    Fireball fb = (Fireball) getHolder().getWorld().spawnEntity(getHolder().getEyeLocation().add(getHolder().getEyeLocation().getDirection().normalize().multiply(2)), EntityType.FIREBALL);
                    fb.setIsIncendiary(true);
                    fb.setYield(explosionSize);
                    Vector unitVector = new Vector(getHolder().getLocation().getDirection().getX(), 0, getHolder().getLocation().getDirection().getZ()).normalize().multiply(2);
                    cooldown = 5;
                    new BukkitRunnable() {
                        @Override
                        public void run() {
                            if (!fb.isDead()) {
                                fb.setVelocity(unitVector);
                            } else {
                                this.cancel();
                            }
                        }
                    }.runTaskTimer(Main.getInstance(), 1L, 1L);
                    new BukkitRunnable() {
                        @Override
                        public void run() {
                            cooldown = 0;
                        }
                    }.runTaskLater(Main.getInstance(), 100L);
                    future.complete(true);
                }

            }
        }.runTask(Main.getInstance());
        return future;
    }
}
```

Then you create a new vehicle config you will need edit to add this part to the yml

```text
    # The name of the class
    className: me.legofreak107.vehiclesplus.vehicles.objects.base.Turret

    # The custom variables in the class
    explosionSize: 3.0

    # The custom variables in the class
    ammo:
      ==: org.bukkit.inventory.ItemStack
      type: TNT

    # The custom variables in the class
    skin:
      ==: org.bukkit.inventory.ItemStack
      type: LEATHER_BOOTS
      damage: 9
      meta:
        ==: ItemMeta
        meta-type: LEATHER_ARMOR
        Unbreakable: true
    color: *id001
    xOffset: -0.5
    yOffset: 0.0
    UID: b120b80f-5f94-42ae-98c6-13b3dc137b3c
    zOffset: 0.0
    isCustomPlaced: false
```

