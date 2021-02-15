---
description: >-
  A not so typical dimension file breakdown. This is likely going to be one of
  the longest section in this documentation. Part 2,  Key Values in Iris
---

# Dim Parameters Part 2

## All Dimensional Key Value Parameters \(Numerical Values\)

These are the Boolean values that are toggle able in the dimension file. The ones below may not have their default values, but are just values set for the purpose of explanations.

```javascript
    "version": 2,
    "biomeZoom": 0,
    "continentZoom": 0,
    "coordFractureDistance": 0,
    "coordFractureZoom": 0,
    "fluidHeight": 0,
    "dimensionAngleDeg": 0,
    "landChance": 0,
    "landZoom": 0,
    "lootTries": 0,
    "regionZoom": 0,
    "rockZoom": 0,
    "terrainZoom": 0,
    "seaZoom": 0,
```

## Version

**The Version of this dimension, Changing this will prevent you from accidentally upgrading your file and corrupting the world.**  
The version of the configuration files in the pack. 

## Fluid Height

**The fluid height for this dimension.**  
The vanilla default is 63, this makes the base water level at 63

## Dimensional Angle

**You can rotate the input coordinates by an angle. This can make terrain appear more natural \(less sharp corners and lines\).**   
This literally rotates the entire dimension by an angle.  Try 12 degrees or something not on a 90 or 45 degree angle. Default Value is 0.0, Maximum allowed is 360.0, Minimum allowed is 0.0

## Land Chance

**The land chance. Up to 1.0 for total land or 0.0 for total sea**  
This is the land to ocean percentage. The minimum is 0, and max is 1. _Our recommendation is 0.625_

## Loot Tries

**Try to fill a container with loot up to this many times to avoid too many empty chests.**  
Defaulted at 5, the amount of times that a global loot table will be tried to place an item inside of a chest, increasing this will fill a chest with things, reducing it will empty. no lower than zero, no higher than 512\* \(you _can_ go higher but why\)

## Coordinate Fracture Distance/Zoom

**Coordinate Zoom:** Higher = less frequent warping, Lower = more frequent and rapid warping / swirls.  
**Coordinate Fracture Distance:** Applies noise to the input coordinates. This creates the 'iris swirls' and wavy features. The distance pushes these waves further into places they shouldn't be. This is a block value multiplier.

## Zooming

**This zooms in the elements by a multiplier:**  
Imagine using a crumpled ball of paper, then zooming into it. that's what this does.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Land Zoom</th>
      <th style="text-align:left">Region Zoom</th>
      <th style="text-align:left">Biome Zoom</th>
      <th style="text-align:left">Terrain Zoom</th>
      <th style="text-align:left">Sea Zoom</th>
      <th style="text-align:left">Rock Zoom</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>Default: <b>1</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>Default: <b>1</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>Default: <b>1</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>Default: <b>2</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>Default: <b>1</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
      <td style="text-align:left">
        <p>Default: <b>5</b>
        </p>
        <p>Min: <b>1.0e-4</b>
        </p>
        <p>Max: <b>512</b>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">This zooms in the land space</td>
      <td style="text-align:left">Change the size of regions</td>
      <td style="text-align:left">This zooms in the biome colors if multiple derivatives are chosen</td>
      <td
      style="text-align:left">This stretches the terrain.</td>
        <td style="text-align:left">This zooms oceanic biomes</td>
        <td style="text-align:left">The rock zoom mostly for zooming in on a wispy palette</td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
Note that for **Terrain zoom** Higher than 2.0 may cause weird rounding artifacts. Lower = more terrain changes per block
{% endhint %}

\*\*\*\*

## Non-Numerical Dimensional Key Values \(yeesh\)

```javascript
    "resourcePack": "",
    "environment": "NORMAL",
    "focus": "",
    "name": "Hello Iris",
```

## Environment

**The world Environment.**  
This is fairly straightforward, only 3 possible options **NORMAL, NETHER,** and **THE\_END.**

## Focus mode \(Helpful\)

**Keep this undefined or empty, setting this to a value will force the overworld to only generate that biome. Great for testing, Must be a valid biome.**  
Focus mode allows you to have a specific biome be the only biome that shows up when you are making your biome. This was used in almost every step of developing the Overworld pack, and others. Below you would only see a desert

#### "focus": "hot-desert",

## Name

**The human readable name of this dimension**  
Name of Dimension. no real explanation needed

