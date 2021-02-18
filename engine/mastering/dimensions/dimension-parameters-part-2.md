---
description: >-
  A not so typical dimension file breakdown. This is likely going to be one of
  the longest section in this documentation. Part 1, Booleans in Iris
---

# Dim Parameters Part 1

## All Dimensional Boolean Parameters \(Boolean Values\)

These are the Boolean values that are toggle able in the dimension file. The ones below may not have their default values, but are just values set for the purpose of explanations.

```javascript
    "carving": false,
    "caves": false,
    "decorate": true,
    "debugSmartBore": false,
    "placeObjects": true,
    "postProcessing": true,
    "postProcessCaves": false,
    "postProcessingSlabs": false,
    "postProcessingWalls": false,
    "preventLeafDecay": false,
    "vanillaCaves": false,
    "vanillaStructures": false,
```

## Carving

**Carve Terrain or not**  
Carving is a 3D Noise layer that will just **CUT** through mountains and terrain, making some neat cliffs in mountain regions. This has a reasonable performance hit, but is on by default- well worth it in out opinion.

## Caves

**Generate Caves or not.**  
Literally just a true or false as to allow iris generate **IRIS caves** not to be confused with **Vanilla Caves**

## Decorate

**Generate Decorations or not.**  
Literally just a true or false as to allow iris generate predefined decorators in each biome. Example: if you have a biome decorator that says to generate flowers, toggling this in the dimension will toggle it everywhere

## Debug Smart Bore

**Instead of filling objects with air, fill with cobweb so you can see**  
This is to help show you where iris thinks blocks are, and are not. It places cobwebs in the air blocks to show you where the **Structure** module thinks it should Cut blocks and stuff out, without overwriting the other surroundings.

## Place Objects

**Disable this to stop placing objects in biomes**  
This is the _'hand that gives, or the hand that takes away'_ in regards to objects. It prevents the placement of all iris schematics in biomes.

## Post Processing

**Use Post Processing or not.**  
Post processing is the unessential, finishing touches that iris does to make the world more pretty, at the cost of a **sleight performance hit**. It is fine to leave this on. If you turn it off, you may not see the **Slabber** , **Pot-Hole-Filler, Nipple-Remover, Stacker-Fixer** working, this is because you just turned them off.

| Slabber | **Pot-Hole-Filler** | Nipple-Remover | Stacker-Fixer |
| :--- | :--- | :--- | :--- |
| The module that puts slabs on slopes for a more natural look. | The generator might make a small hole, Iris will remove this. | The generator might make a small bump, Iris will remove this. | Prevents the rare occurrence, of buttons stacking as a decorator. |

## Post Process Caves

**Use post processing in caves or not**  
Post processing is the unessential, finishing touches that iris does to make the world more pretty, at the cost of a **sleight performance hit**. It is fine to leave this on. If you turn it off, you may not see the **Slabber** , **Pot-Hole-Filler, Nipple-Remover, Stacker-Fixer** working, this is because you just turned them off. See [post processing](dimension-parameters-part-2.md#post-processing) for an explanation.

## Post Processing Slabs/Walls

**Add Slabs or walls to the post processor instead.**  
Post processing is the unessential, finishing touches that iris does to make the world more pretty, at the cost of a **sleight performance hit**. It is fine to leave this on. If you turn it off, you may not see the **Slabber** , **Pot-Hole-Filler, Nipple-Remover, Stacker-Fixer** working, this is because you just turned them off. See [post processing](dimension-parameters-part-2.md#post-processing) for an explanation.

## Prevent Leaf Decay

**Prevent Leaf Decay**  
Whenever iris places a schematic, or anything leaf related- especially with big trees. We use this in iris Overworld Dimension for the trees we place.

## Vanilla Caves

**Generate Vanilla caves and Cave things**  
Working vanilla caves that can intersect with iris caves. this creates some gnarly looking caves and ravines.

## Vanilla Structures

**Generate Vanilla Structures**  
Currently not working in the way that you might intend, this for now is **default to false** because it cause instability, gen failure, and other sorts of issues. We plan to just make out own villages in the future.

