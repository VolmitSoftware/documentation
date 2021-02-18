---
description: This page will go over Basics in Regions
---

# Regions

## Topics

1. [Video Tutorial](regions.md#video-tutorial)
2. [Introduction](regions.md#introduction)
3. [Default in the example](regions.md#default-in-the-example)
4. [Settings](regions.md#settings)
   1. [Name \*](regions.md#1-name)
   2. [Land, Sea & Shore Biomes \*](regions.md#2-land-sea-and-shore-biomes)
   3. [Cave, Lake & River Biomes](regions.md#3-cave-lake-and-river-biomes)
   4. [Biome Zooming](regions.md#4-biome-zooming)
   5. [Ridge Biomes](regions.md#5-ridge-biomes)
   6. [Spot Biomes](regions.md#6-spot-biomes)
   7. [Shore Ratio](regions.md#7-shore-ratio)
   8. [Rivers](regions.md#8-rivers)

{% hint style="info" %}
Every setting with a `*` is mandatory for this file
{% endhint %}

## Video Tutorial

> To be added later

## Introduction

Regions are the JSON Equivalent of a Library Subsection, where the books are the biomes, and each biome can tell a story. In normal language; Regions are a way for you to map biomes in your world, and have a system that lets you control all biomes of a certain type \(in this region\) with a single file.

{% hint style="success" %}
Since a lot of the settings you can change here can also be changed in each of the biomes individually, we will only go over region-only settings here. This is not the case for the Mastering part, where we will include all settings.
{% endhint %}

## Default in the example

The region files can be found in the `regions` folder and usually have a descriptive name. We will be using the region `"hot"` as found in the example project:

```javascript
{
    "name": "Hot",
    "landBiomes": [
        "desert"
    ],
    "seaBiomes": [
        "ocean"
    ],
    "shoreBiomes": [
        "beach"
    ],
    "caveBiomes": [
        "mountains"
    ],
    "lakeBiomes": [
        "beach"
    ],
    "riverBiomes": [
        "ocean"
    ],
    "landBiomeZoom": 1,
    "seaBiomeZoom": 1,
    "shoreBiomeZoom": 1,
    "caveBiomeZoom": 1,
    "lakeBiomeZoom": 1,
    "riverBiomeZoom": 1,
    "ridgeBiomes": [
        {
            "biome": "swamp-forest",
            "type": "LAND",
            "chance": 1
        }
    ],
    "spotBiomes": [
        {
            "biome": "oak-forest",
            "type": "LAND",
            "rarity": 1
        }
    ],
    "shoreRatio": 0.01,
    "rivers": true
}
```

## Settings

### 1 - Name \*

```javascript
"name": "Hot"
```

The name of the region. It is best to keep / make this the same as the name of the file you are editing.

### 2 - Land, Sea & Shore Biomes \*

```javascript
"landBiomes": [
    "desert"
],
"seaBiomes": [
    "ocean"
],
"shoreBiomes": [
    "beach"
],
```

Here you specify the biomes in the world as they connect to eachother. `"landBiomes"` only connect to `"shoreBiomes"` and `"seaBiomes"` only connect to `"shoreBiomes"` as well. `"shoreBiomes"` connect land with sea.

### 3 - Cave, Lake & River Biomes

```javascript
"caveBiomes": [
    "mountains"
],
"lakeBiomes": [
    "beach"
],
"riverBiomes": [
    "ocean"
],
```

These biomes are optional and have certain properties:

* `"caveBiomes"` can only spawn next to `"landBiomes"`,
* `"lakeBiomes"` can spawn next to `"landBiomes"` and `"shoreBiomes"`, and
* `"riverBiomes"` can spawn connected to all other biome types.

### 4 - Biome Zooming

```javascript
"landBiomeZoom": 1,
"seaBiomeZoom": 1,
"shoreBiomeZoom": 1,
"caveBiomeZoom": 1,
"lakeBiomeZoom": 1,
"riverBiomeZoom": 1
```

All of the previous biome types have zooming factors to them. Making this number higher will make the biomes larger.

### 5 - Ridge Biomes

```javascript
"ridgeBiomes": [
    {
        "biome": "swamp-forest",
        "type": "LAND",
        "chance": 1
    }
]
```

Ridge biomes are like real-life mountain chains:

![A real-life mountain-ridge &quot;biome&quot;](../../.gitbook/assets/image%20%281%29.png)

![A Minecraft \(Iris\) ridge biome](../../.gitbook/assets/image%20%2820%29.png)

![A real-life river-ridge &quot;biome&quot;](../../.gitbook/assets/image%20%286%29.png)

These biomes have a few properties:

{% tabs %}
{% tab title="Biome" %}
```javascript
"biome": "swamp-forest"
```

Here you specify the type of biome that should spawn as a ridge \(a straight but fractal line through the land\).
{% endtab %}

{% tab title="Type" %}
```javascript
"type": "LAND"
```

Here you specify the type of terrain ridges should spawn on, can be any of the previous types \(`"SHORE"`, `"LAND"`, `"SEA"`, `"CAVE"`, `"RIVER"`, and `"LAKE"`\) and `"DEFER"`, where the last option uses a random type every time \(not always the same\).
{% endtab %}

{% tab title="Chance" %}
```javascript
"chance": 1
```

Here you specify the chance that the biome will continue and / or spawn in any given location on the previously specified `"type"` terrain. Ranges from 0 \(never\) to 1 \(frequently\).

{% hint style="warning" %}
For the use of [Spot Biomes](regions.md#6-spot-biomes), this setting is replaced by `"rarity",`but functions the same.
{% endhint %}
{% endtab %}
{% endtabs %}

### 6 - Spot Biomes

```javascript
"spotBiomes": [
    {
        "biome": "oak-forest",
        "type": "CAVE",
        "rarity": 1
    }
]
```

Spot biomes are very similar to the [Ridge Biomes](regions.md#4-ridge-biomes), all settings for this are explained there. These biomes can make for very interesting looks in the world, such as this real-life example:

![Hillier lake &quot;Spot-Biome&quot; in western Australia](../../.gitbook/assets/image%20%285%29.png)

![Minecraft \(Iris\) Spot-biome ](../../.gitbook/assets/image%20%289%29.png)

### 7 - Shore Ratio

```javascript
"shoreRatio": 0.13
```

This affects how "deep" the shores \(beaches\) are compared to the land. Making this 1 will make for very, very deep shores.

![Example of what the world may look like when making this setting a high number \(e.g. 0.8\)](../../.gitbook/assets/image%20%2811%29.png)

### 8 - Rivers

```javascript
"rivers": true
```

Places vanilla rivers in the world if turned to `true` and not if `false`.

## Mastering

If you cannot find the settings you're looking for here, check out the [Template Mastering Page](regions.md)

