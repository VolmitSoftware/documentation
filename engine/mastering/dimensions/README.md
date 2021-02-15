---
description: >-
  A not so typical dimension file breakdown. This page specifically is going to
  explain the default, parameters. these parameters WILL be covered in the
  elsewhere the same. this is a quick start
---

# Dimensions

{% hint style="warning" %}
This page has not yet been updated in accordance with the new structure. Most information should still be valid, but keep this warning in mind.
{% endhint %}

{% tabs %}
{% tab title="Default" %}
{% code title="exampleDimension.json" %}
```javascript
{
    "postProcessing": false,
    "environment": "NORMAL",
    "regions": [
        "hot",
        "temperate",
        "temperate",
        "cold"
    ],
    "caves": false,
    "focus": "",
    "name": "Example",
    "fluidHeight": 63,
    "carving": false,
    "version": 1
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

## Post Processing

**Use Post Processing or not.**  
Post processing is the unessential, finishing touches that iris does to make the world more pretty, at the cost of a **sleight performance hit**. It is fine to leave this on. If you turn it off, you may not see the **Slabber** , **Pot-Hole-Filler, Nipple-Remover, Stacker-Fixer** working, this is because you just turned them off. \(More on Post Processing [here](dimension-parameters-part-2.md#post-processing)\)

## Environment

**The world Environment.**  
This is fairly straightforward, only 3 possible options **NORMAL, NETHER,** and **THE\_END.**

## Regions \(Essential\)

**Define all regions to include in this dimension.**  
This is **essential** for any dimension file. The listings in here are required for you to see any kind of impact or biomes generate. 

#### IF YOU WANT ANYTHING TO GENERATE YOU NEED TO HAVE BIOMES IN REGIONS, AND REGIONS IN THE DIMENSION FOLDER!

## Caves 

**Generate Caves or not.**  
Literally just a true or false as to allow iris generate **IRIS caves** not to be confused with **Vanilla Caves**

## Focus mode \(Helpful\)

**Keep this undefined or empty, setting this to a value will force the overworld to only generate that biome. Great for testing, Must be a valid biome.**  
Focus mode allows you to have a specific biome be the only biome that shows up when you are making your biome. This was used in almost every step of developing the Overworld pack, and others. Below you would only see a desert

#### "focus": "hot-desert",

## Name

**The human readable name of this dimension**  
Name of Dimension. no real explanation needed

## Carving 

**Carve Terrain or not**  
Carving is a 3D Noise layer that will  just **CUT** through mountains and terrain, making some neat cliffs in mountain regions. This has a reasonable performance hit, but is on by default- well worth it in out opinion.

## Version

**The Version of this dimension, Changing this will prevent you from accidentally upgrading your file and corrupting the world.**  
The version of the configuration files in the pack.

## Post Overview

We highly recommend that you familiarize yourself, and toy around with them before diving straight into the heavy lifting- that is, **dimensional manipulation**. \(that sounds funny\) But in all seriousness the Dimensional file is likely the hardest of the files to learn, as all are relatively self explanatory in most other circumstances.



