---
description: This page will go over Basics in Dimensions
---

# Dimensions

## Topics

1. [Video Tutorial](dimensions.md#video-tutorial)
2. [Introduction](dimensions.md#introduction)
3. [Default in the example](dimensions.md#default-in-the-example)
4. [Settings](dimensions.md#settings)
   1. [Name \*](dimensions.md#1-name)
   2. [Version \*](dimensions.md#2-version)
   3. [Environment \*](dimensions.md#3-environment)
   4. [Regions \*](dimensions.md#4-regions)
   5. [Fluid Height \*](dimensions.md#5-fluid-height)
   6. [Vanilla Ravines, Caves & Structures](dimensions.md#6-vanilla-caves-and-structures)
   7. [Biome & Region Zoom](dimensions.md#7-biome-zoom)
   8. [Focus](dimensions.md#8-focus)
   9. [Land Chance](dimensions.md#9-land-chance)
   10. [Ores](dimensions.md#10-ores)

{% hint style="info" %}
Every setting with a `*` is mandatory for this file
{% endhint %}

## Video Tutorial

> To be added later

## Introduction

Dimensions are `json` files and they are placed in the `dimensions` folder. Typically you only have one dimension file in your entire project. The dimension file is the first and highest level file Iris looks at when generating. It describes regions, and other base settings.

This file is the most impactful on your world as it controls every region, and every region controls every biome.

{% hint style="success" %}
This is a relatively large and complex file and it is where people can get discouraged to continue using Iris' configurations.

Though, you have come this far already, so we are happy to tell you that you will only touch the Dimension files a couple times during your time editing in Iris. This is among the reasons that this page has relatively little settings.
{% endhint %}

When working on a Biome or Region we recommend that you **Focus** the biomes that you are working \(only 1 at a time\), If you are working on the terrain, we recommend that you turn off **Decorate** as to be able to see it better. As for **Regions**- they are like the bag holding all the biomes, but you can have as many regions in the dimension file as you want, as long as they are not duplicated.

## Default in the example

The dimension file is called `example.json` and can be found in the `dimensions` folder:

```javascript
{
    "name": "Example",
    "version": 1,
    "environment": "NORMAL",
    "regions": [
        "hot",
        "hot"
    ],
    "fluidHeight": 63,
    "ravines": false,
    "vanillaCaves": false,
    "vanillaStructures": false,
    "biomeZoom": 1,
    "regionZoom": 1,
    "focus": "",
    "landChance": 0.625,
    "deposits": [
        {
            "minHeight": 1,
            "maxHeight": 256,
            "minPerChunk": 5,
            "maxPerChunk": 20,
            "minSize": 10,
            "maxSize": 20,
            "varience": 10,
            "palette": [
                {
                    "block": "andesite"
                }
            ]
        }
    ]
}
```

{% hint style="info" %}
You may notice `"hot"` is specified twice. This is merely to show you how to add multiple items to the array. Adding `"cold"` region now will mean 2/3rds `"hot"` and 1/3rd `"cold"`

You may notice `"focus"` being empty, this means that it does nothing.  
This is required so we can see the changes made to other biomes.
{% endhint %}

## Settings

### 1 - Name \*

```javascript
"name": "Example"
```

Here you can specify the name of the dimension. This should be the same as the name of the file we are currently editing, so `example`, this file must, in turn, should be called the same as the project we are working in, again `example`. This can be anything you want \(some limitations\), but try keeping these three the same.

### 2 - Version \*

```javascript
"version": 1
```

This is where you specify the version of the settings. This prevents you from breaking stuff where it's not supposed to. You do not have to change this value, but it may be useful when you are editing and want to keep track of the current version.

### 3 - Environment \*

```javascript
"environment": "NORMAL"
```

This affects the type of world you are in and can be any of three: `"NORMAL"`, `"NETHER"`, `"THE_END"` for the Overworld, Nether and the End, respectively. \(Affects the color of the sky and mob spawning defaults etc.\)

### 4 - Regions \*

```javascript
"regions": [
    "hot",
    "hot"
]
```

Here you specify the [regions ](regions.md)which you want to have spawning [biomes ](biomes.md)in your world. The names here are and must be the exact same as the names of the files in the `regions` folder.

### 5 - Fluid Height \*

```javascript
"fluidHeight": 63
```

Here you can specify the height of the water level. Ranges between 0 and 255.

{% hint style="warning" %}
This does not raise the relative level of the water in the world, but rather moves the entire terrain up. This is caused by the way biomes spawn: relative to the water level. \(See the [Biomes' Generators Setting](biomes.md#4-generators)\)
{% endhint %}

### 6 - Vanilla Ravines, Caves & Structures

```javascript
"ravines": false,
"vanillaCaves": false,
"vanillaStructures": false
```

These toggles can turn on `true` and turn off `false` vanilla ravines, caves and structures. Note that the ravines and caves do not have the decoration block you may have specified.

### 7 - Biome & Region Zoom

```javascript
"biomeZoom": 1,
"regionZoom": 1
```

This setting zooms your biomes and region respectively. A higher number will give larger biomes & region respectively. Ranges between 0.0001 and 512.

### 8 - Focus

```javascript
"focus": ""
```

This setting will normally not be used in your world, but is very useful when you want to see only one biome in your world. Setting this to any biome will make that the only biome that can spawn. Must be a valid biome.

### 9 - Land Chance

```javascript
"landChance": 0.625
```

Here you can modify the ratio between ocean and land biomes in the world. Ranges from 0 \(no land biomes\) and 1 \(only land biomes\).

### 10 - Ores

```javascript
"deposits": [
    {
        "minHeight": 1,
        "maxHeight": 256,
        "minPerChunk": 5,
        "maxPerChunk": 20,
        "minSize": 10,
        "maxSize": 20,
        "varience": 10,
        "palette": [
            {
                "block": "andesite"
            }
        ]
    }
]
```

In the `"deposits"` setting you can specify the ores you want to spawn in the ground. These ores have a few properties:

{% tabs %}
{% tab title="Min- & MaxHeight" %}
```javascript
"minHeight": 1,
"maxHeight": 256
```

Here you can specify the height at which these ores can spawn. For example, setting `"maxHeight"` to 30 with redstone ore would make sure the ores only spawn below level 30
{% endtab %}

{% tab title="Min- & MaxPerChunk" %}
```javascript
"minPerChunk": 5,
"maxPerChunk": 20
```

Here you can specify the amount of ore patches that spawn per chunk. Setting this to 5 and 20, like in the example, will make sure there are at least 5 and at most 20 patches per chunk.
{% endtab %}

{% tab title="Min- & MaxSize" %}
```javascript
"minSize": 10,
"maxSize": 20
```

Here you can specify the size of each of the patches. Setting it to 10 and 20, like in the example, will make each patch consist of at least 10 and at most 20 blocks.
{% endtab %}

{% tab title="Varience" %}
```javascript
"varience": 10
```

Here you can specify the amount of different shapes of patches Iris will create. Making this very high will cause a lot of lag since Iris has to create all of these as objects, making this too low will make it so that all the patches look very similar. Note that these patches can be rotated along the y-axis.
{% endtab %}

{% tab title="Palette" %}
```javascript
"palette": [
    {
        "block": "andesite"
    }
]
```

In the palette you specify information about the blocks used in this patch. You can use multiple blocks by adding more objects at the bottom like this:

```javascript
"palette": [
    {
        "block": "andesite",
        "weight": 2
    },
    {
        "block": "diorite"
        "weight": 1
    }
]
```

{% hint style="info" %}
You may notice the `"weight"` property. This indicates how much this block should spawn relatively to others. The current setup \(2 for andesite and 1 for diorite\) will make andesite twice as likely as diorite for each of the blocks in the patch
{% endhint %}

You can also specify block data here, which is used for rotating stairs etc, and is required for enabling the use of modded blocks. Example \(will make the fence waterlogged\):

```javascript
"palette": [
    {
        "block": "oak_fence",
        "data": {
            "waterlogged": true
        }
    }
]
```
{% endtab %}
{% endtabs %}

{% hint style="success" %}
You can also specify ores in region and biome files separately. This is done in the same manner as described here.
{% endhint %}

## Mastering

If you cannot find the settings you're looking for here, check out the [Dimensions Mastering Page](../mastering/dimensions/).

