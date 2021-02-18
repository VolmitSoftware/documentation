---
description: >-
  A not so typical dimension file breakdown. This is likely going to be one of
  the longest section in this documentation. Part 2,  Key Values in Iris
---

# Dim Parameters Part 3

## All Dimensional Array/Set/Objected Parameters

These are the values that list, compile, or involve other objects in the dimension file. The ones below may not have their default values, but are just values set for the purpose of explanations. **All of these have a default value so you don't need all of these values, this is merely just to tell you what they do.**

{% tabs %}
{% tab title="All Object Values " %}
```javascript
// These are the Non-Style Based Object Values
    "blockDrops": [],
    "carveLayers": [],
    "deposits": [],
    "entityInitialSpawns": [],
    "entitySpawnOverrides": [],
    "fluidPalette": {},
    "loot": {},
    "mutations": [],
    "overlayNoise": [],
    "rockPalette": {},
    "sky": {},
    "text": [],

// These are All Style Based Object Values
    "regionStyle": {},
    "caveBiomeStyle": {},
    "continentalStyle": {},
    "islandBiomeChanceStyle": {},
    "islandBiomeStyle": {},
    "lakeBiomeStyle": {},
    "landBiomeStyle": {},
    "riverBiomeStyle": {},
    "seaBiomeStyle": {},
    "shoreBiomeStyle": {},
    "skylandBiomeStyle": {},
```
{% endtab %}

{% tab title="All Object Values Expanded" %}
```javascript

```
{% endtab %}
{% endtabs %}

### Block Drops

**Define custom block drops for this dimension**  
Block Drops are the **items** that are dropped when broken, or are tossed into chests as **loot**. Drops are a **UNIVERSAL PARAMETER,** Here is the link for a TOTAL Breakdown of this \[[Here](../universal-parameters/#drops-breakdown)\]

### Carve Layers

**Define carve layers, If you put this in the file you need to have it defined or remove it. it will cause problems.** the carve layers are

<table>
  <thead>
    <tr>
      <th style="text-align:left">Max Height</th>
      <th style="text-align:left">Min Height</th>
      <th style="text-align:left">Style</th>
      <th style="text-align:left">Threshold</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">The highest possible carve layer.</td>
      <td style="text-align:left">The lowest possible carve layer.</td>
      <td style="text-align:left">This is a complex topic, go <a href="../universal-parameters/#style-breakdown">here</a> for
        explanation.</td>
      <td style="text-align:left">
        <p>carved = (x,y,z) &gt; Threshold</p>
        <p>Between 0 and 1</p>
        <p>this is a multiplier.</p>
      </td>
    </tr>
  </tbody>
</table>

### Cave Layers

**Define cave layers, If you put this in the file you need to have it defined or remove it. it will cause problems.**

| Can Break Surface | Cave Thickness | Cave Zoom |
| :--- | :--- | :--- |
| The highest possible carve layer. | The lowest possible carve layer. | This is a complex topic, go [here](../universal-parameters/#style-breakdown) for explanation |

| Fluid | Horizontal Slope | Vertical Slope |
| :--- | :--- | :--- |
| Fluid is child of a layer, in this case its the cave layer. see [here ](../universal-parameters/#fluid-breakdown)for more info. | This is the horizontal slope that a cave generators follows. Learn about slope [here](../universal-parameters/#slope-breakdown). | This is the vertical slope that a cave generators follows. Learn about slope [here](../universal-parameters/#slope-breakdown). |

### Deposits

**Define biome deposit generators that add onto the existing regional and global deposit generators**  
This is the best way to set ORES that are for the dimension: Overworld, or Nether etc. This can also be set in a REGION or in a BIOME. To see Usage go \[[Here](../universal-parameters/#breakdown)\]

### Entity Initial Spawns

**Represents an entity spawn during initial chunk generation**  
When an entity is spawned this is run to determine any interaction with that spawn. This is usually a list of objects \(entities\)

| Entity | Max Spawns | Min Spawns | Rarity |
| :--- | :--- | :--- | :--- |
| This is the entity, if you have a plugin that has a unique ID entity, put that here. EG: "COW" | Max of this entity to spawn on a Single entity chance Spawn | Min of this entity to spawn on a Single entity chance Spawn | The rarity of the Spawn, Min=1, higher = more rare |

### Entity Spawn Overrides

| Cancel Source Spawn | Entity | Rarity | Trigger |
| :--- | :--- | :--- | :--- |
| This is a Boolean that prevents the spawn of 'entity' if trigger is passed. | This is the entity, if you have a plugin that has a unique ID entity, put that here. EG: "COW" | The rarity of the Spawn, assuming the trigger is not false, Min=1, higher = more rare | In the event of "ENTITY" spawns, This trigger is true. |

**This represents the Event of an event spawn**  
When an entity is spawned this is run to determine any interaction with that spawn. This is usually to either challenge that, or change that

### **Fluid Palette**

**The palette of blocks for fluid**  
This is the palette where you set what the fluid is going to be. This is what is generally water in the Overworld, only 1 water-level fluid can be set, you can use sub-water layers using [\[Fluid\]](../universal-parameters/#fluid-breakdown) subsets in other parents. To learn about how to use palettes go [here](../universal-parameters/#palette-explained). Zoom is the only really specific information that is unique, this only uses the style, and multiplies a zoom scale, default at 1.

### **L**oot

**Try to fill a container with loot up to this many times to avoid too many empty chests.**  
Loot tables are unique to each file. The Dimensional files are global loot, Region and Biome loot all have their own files respectively. To learn about loot go [here](../universal-parameters/#drops-explained).

### Mutations

**Define biome mutations for this dimension**  
Mutations are an interesting example of Subdivided Biomes. Whenever a biome is next to another biome, you will get a have a connection between the two, this is a great way to cross-fade trees when you have biomes mixing. You need to make the trees and organics that you want to show up, this is meerly just a region where things will propagate. Below is an example of a mutation file

{% tabs %}
{% tab title="Mutation" %}
```javascript
   "mutations": [
        {
            "checks": 8,
            "objects": [
                {
                    "chance": 0.4,
                    "density": 1,
                    "rotation": {
                        "yAxis": {
                            "min": 0,
                            "max": 0,
                            "interval": 90,
                            "enabled": true
                        },
                        "enabled": true
                    },
                    "place": [
                        "dual-tree/corrupted-swamp-1",
                        "dual-tree/corrupted-swamp-2",
                    ]
                }
            ],
            "radius": 12,
            "sideB": [
                "mushroom-forest",
            ],
            "sideA": [
                "swamp-roofed-forest",
            ]
        }
```
{% endtab %}
{% endtabs %}

| Checks | Objects | Radius | Side A/B |
| :--- | :--- | :--- | :--- |
| How many times Per chunk will this check for a connection | This is what iris does to the objects, look here to see what happens to the objects | This is a per-block scan radius for placing this mutation | This determines the sides of the mutation, this name is the name of the biome file. |

### Overlay Noise

**Overlay additional noise on top of the interpolated terrain.**  
For example, if you want to overlay IRIS dtyle generator over a flat terrain of the global dimension you can do that here. See [Generator ](../universal-parameters/#style-generator-breakdown)to see how to use generators, and the min and max values just affect the min and max block value changes.

### Rock Palette

**The palette of blocks for 'stone'**  
Assuming that you are in the ground, what are the stones around you going to look like? but this involves [Style](../universal-parameters/#style-generator-breakdown), and [Palette](../universal-parameters/#palette-breakdown), with zoom, that zoom just being a multiplier of the zoom in or out as usual.

### Sky

**Literally the Sky Create an inverted dimension in the sky \(like the nether\)**  
This is essentially creating an additional terrain layer directly above you. \(inverted\) if you want to learn how to use this, it had every single possible parameter that Overworld has. LMAO see[ Dimension Basics](../../understanding/dimensions.md) for that. you can put everything that you have in the Overworld in here and you will get a mirror of the Overworld

## ALL STYLE BASED OBJECTIVE VALUES

All of these have the SAME usage, please refer [here](../universal-parameters/#style-generator-breakdown), to understand how to use style. This specific area will just tell you what they are for

* Region Style
  * Placement style of regions
* Cave Biome Style
  * Placement style of cave biomes
* Continental Style
  * Placement of land/sea
* Island Biome Chance Style
  * Placement style of biomes \(fractal water looks cool\)
* Island Biome Style
  * Placement style of island Biomes
* Lake Biome Style
  * Placement style of lake biomes
* Land Biome Style
  * Placement style of land/Overworld biomes
* River Biome Style
  * Placement style of river biomes
* Sea Biome Style
  * Placement style of sea biomes
* Shore Biome Style
  * Placement style of shore biomes
* Skyland Biome Style
  * Placement style of Biomes that are set above the terrain

