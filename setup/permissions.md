---
description: A list of permissions and what they pertain to
---

# Permissions

## Command Permissions

### Player Commands

#### vp.garage

Access the `/v garage` command

#### vp.shop

Access the `/v shop` command

#### vp.fuel.buy

Access the `/fuel buy` command

#### vp.fuel.shop

Access the `/fuel shop` command

### Admin Commands

#### vp.admin.list

Access the `/v list` command

#### vp.admin.give

Access the `/v give` command

#### vp.admin.forceshop.fuel

Access the `/fuel forceshop` command

#### vp.admin.forceshop.vehicles

Access the `/v forceshop` command

#### vp.admin.forcegarage

Access the `/v forcegarage` command

#### vp.admin.fuel.give

Access the `/fuel give` command

#### vp.admin.givepart

Access the `/addon givepart` command

#### vp.admin.givepaint

Access the `/addon givepaint` command

#### vp.admin.givewheel

Access the `/addon givewheel` command

## Extra permissions

**vp.buy.&lt;Type&gt;**

_This is a default permission, and can be changed per every base vehicle._  
Players with this permission are able to buy this vehicle from the shop.

Example:

Let's say you have a base vehicle named `SuperCoolCar`. If you go to `plugins/VehiclesPlusPro/vehicles/cars/SuperCoolCar.yml`, you will find these lines:

```yaml
permissions:
  className: me.legofreak107.vehiclesplus.vehicles.vehicles.objects.VehiclePermissions
  buyPermission: vp.buy.car
  ridePermission: vp.ride.car
```

On the `buyPermission` line, you can customize the permission that players/groups must have to access this vehicle.

**vp.ride.&lt;Type&gt;**

_This is a default permission, and can be changed per every base vehicle._  
Players with this permission are able to enter this vehicle from the shop.  
If `enterWithoutRidePermission` ****is enabled for this vehicle, the player can join the non-steer seats without the permission.

Example:

Let's say you have a base vehicle named `SuperCoolCar`. If you go to `plugins/VehiclesPlusPro/vehicles/cars/SuperCoolCar.yml`, you will find these lines:

```yaml
permissions:
  className: me.legofreak107.vehiclesplus.vehicles.vehicles.objects.VehiclePermissions
  buyPermission: vp.buy.car
  ridePermission: vp.ride.car
```

On the `ridePermission` line, you can customize the permission that players/groups must have to ride in the vehicle.

#### vp.admin.modify.other

Players with this permission have the ability to access and modify other players’ vehicles

#### vp.mechanic

Players with this permission have the ability to open the upgrades menu in a vehicle

