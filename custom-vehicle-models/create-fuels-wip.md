# Create fuels \(WIP\)

{% hint style="warning" %}
Please visit our [legacy wiki](https://github.com/VolmitSoftware/VehiclesPlus/wiki) to begin creating new vehicles
{% endhint %}

## Step 1

Go into the fuels folder and copy the Gasoline.yml

## Step 2

Rename the newly copied file to the new fuel you want to make

## Step 3

Open the newly created file, it should look something like this

```text
className: me.legofreak107.vehiclesplus.vehicles.objects.fuel.FuelType
name: Gasoline
pricePerLiter: 1.5
fuelItem:
  ==: org.bukkit.inventory.ItemStack
  type: LAVA_BUCKET
```

## Step 4

Edit the values in this file to match your desired rim design

The fuelitem will be the model of the jerrycan

The pricePerLiter will be the price of the fuel per liter

The name will be the name of the fuel

## Step 5

Restart the server

