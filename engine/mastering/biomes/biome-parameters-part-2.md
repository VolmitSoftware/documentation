---
description: >-
  A not so typical Biome file breakdown. This is going to cover the Object based
  values in the biomes file. All of the flags and objects, and changes can all
  be found here and on the previous page
---

# Biome Parameters Part 2



```javascript
{
"biomeScatter": [],
"biomeSkyScatter": [],
"childStyle": {},
"biomeStyle": {},
"blockDrops": [],
"children": [],
"debugColor": "",
"decorators": [],
"deposits": [],
"effects": [],
"entityInitialSpawns": [],
"entitySpawnOverrides": [],
"fluidType": "",
"generators": [],
"layers": [],
"loot": {},
"objects": [],
"seaLayers": [],
"slab": {},
"structures": [],
"text": [],
"wall": {}
}
```

## Biome Scatter

**You can instead specify multiple biome derivatives to randomly scatter colors in this biome FLOOR.**  
This sets the gradients of colors that are done by derivatives, this is great to set the ground colors to look bruised or else-wise.

## Biome Sky Scatter

**You can instead specify multiple biome derivatives to randomly scatter colors in this biome SKY.**  
Since 1.13 supports 3D biomes, you can add different derivative colors for anything above the terrain. \(Think swampy tree leaves with a desert looking grass surface\) This is a great way for setting a 3D color dynamic in leaves or in biome-sky related changes.

## Child Style

**The child \(if set\) shape if, and when it is generated**  
If this biome has children biomes, and the gen layer chooses one of this biomes children, How will it be shaped? The [map ](biome-parameters-part-1.md#debug-color)represents the biomes/children very well, See [Style](../universal-parameters/#style-generator-breakdown) to see how to use it

## Biome Style

**Carve Terrain or not**  
This changes the dispersion of the biome colors if multiple derivatives are chosen. Please See [Style](../universal-parameters/#style-generator-breakdown) to see how to use it, this is just a shape filter

## Block Drops

**Define custom block drops for this biome**  
Drops are the **items** that are dropped when broken**. This is a universal parameter** see [here ](../universal-parameters/#drops-breakdown)to see how to use it.

## Children 

**Have a biome generate in the midst of this biome**  
List any biome names \(file names without.json\) here as children. Portions of this biome can sometimes morph into their children. Iris supports cyclic relationships such as A &gt; B &gt; A &gt; B. **Iris will stop checking 9 biomes down the tree**.

## Decorators

**Decorators are used for things like tall grass, bisected flowers, and even kelp or cactus \(random heights\)**  
This is the best place where you can set the flowers, and organics that are in a per biome basis. 

## Deposits

**Creates ore & other block deposits underground**  
This ADDS this list of deposits to the dimensional/regional parent. This is explained [here](../universal-parameters/#deposits-breakdown), this can be set for multiple parents thus its a dimensional parameter

## Effects \*

**Effects that play in this biome.**  
Effects are ambient effects such as potion effects, random sounds, or even particles around each player. This has a large explanation [here](../universal-parameters/#effects).

## Entity Initial Spawns

**Entity spawns during generation**  
What entity spawns here during the generation of this world. This may soon have support for mythic/other mob providers in the future

## Entity Spawn Overrides

**If the following entity type spawns, spawn this entity. Set to unknown for any entity spawn.**  
This is a fantastic way to prevent the spawn of a cow or any other vanilla spawned mobs. Maybe Mythic mobs in the future etc...

## Generators

**Generators are a form of STYLE generators:**

Style/Generator is the 4-D _\(that's one more D than 3D\)_ rules that draw the carve layer. Please refer to the Universal Parameters [here ](../universal-parameters/#style-generator-breakdown)to see the usage of generators

## Layers

  


## Loot

**What Generates in conatiners here in this biome**  
This is a global parameter, and a regional, AND a biome parameter. [this ](../universal-parameters/#loot-explained)is a great breakdown of loot. Beware that by default this stacks with other parent loot rolls unless otherwise specified

## Objects 

  


## Sea Layers

  


## Slab

  


## Structures

  


## Text

**This is an interesting way to quite literally put text on the surface**  
Please refer to [this](../universal-parameters/#text), for a full explanation of how to use this interesting tool. you can make a trademark per biome if you wanted. the possibilities are strangely endless.

## Wall

  


