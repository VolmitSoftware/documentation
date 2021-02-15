---
description: A tutorial on how to create new rims
---

# Create rims \(WIP\)

{% hint style="warning" %}
Please visit our [legacy wiki](https://github.com/VolmitSoftware/VehiclesPlus/wiki) to begin creating new vehicles
{% endhint %}

## Step 1

Go into the rims folder and copy the Default.yml

## Step 2

Rename the newly copied file to the new rim you want to make

## Step 3

Open the newly created file, it should look something like this

```text
className: me.legofreak107.vehiclesplus.vehicles.objects.rims.RimDesign
skin:
  ==: org.bukkit.inventory.ItemStack
  type: LEATHER_CHESTPLATE
  damage: 2
  meta:
    ==: ItemMeta
    meta-type: LEATHER_ARMOR
    Unbreakable: true
price: 1000.0
name: default
```

## Step 4

Edit the values in this file to match your desired rim design

The skin will be the model of rim

The price will be the price of the rim

The name will be the name of the rim

## Step 5

Restart the server

