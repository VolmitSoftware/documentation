---
description: This page will go over Basics in Biomes
---

# Biomes

## Topics

1. [Video Tutorial](biomes.md#video-tutorial)
2. [Introduction](biomes.md#introduction)
3. [Default in the example](biomes.md#default-in-the-example)
4. [Settings](biomes.md#settings)
   1. [Name \*](biomes.md#1-name)
   2. [Derivative \*](biomes.md#2-derivative)
   3. [Layers \*](biomes.md#3-layers)
   4. [Generators \*](biomes.md#4-generators)
   5. [Objects](biomes.md#5-objects)
   6. [Decorators](biomes.md#6-decorators)
   7. [Slab](biomes.md#7-slab)
   8. [Rarity](biomes.md#8-rarity)
   9. [Debug Color](biomes.md#9-debug-color)
   10. [Loot](biomes.md#10-loot)

{% hint style="info" %}
Every setting with a `*` is mandatory for this file
{% endhint %}

## Video Tutorial

> To be added later

## Introduction

Biomes are `json` files and they are placed in the `biomes` folder. Biomes are what you would expect. They define block types, layers, objects and a lot of other stuff in the world. This is also where you reference noise generators to get your terrain shape.

{% hint style="success" %}
A friendly reminder to keep using `ctrl`+`space`for autocompletions, it makes live so much easier :\)

Also - not all settings hare handeled here, so make sure to check out [Biome Mastering ](biomes.md#mastering)for more
{% endhint %}

## Default in the example

The template file is called `templatefile.json` and can be found in the `template` folder:

```javascript
{
    "name": "Beach",
    "derivative": "BEACH",
    "layers": [
        {
            "palette": [
                {
                    "block": "sand"
                }
            ]
        },
        {
            "style": {
                "style": "STATIC"
            },
            "palette": [
                {
                    "block": "dirt"
                }
            ],
            "minHeight": 2,
            "maxHeight": 3
        }
    ],
    "generators": [
        {
            "generator": "vanilla",
            "max": 2,
            "min": -4
        }
    ],
    "objects": [
        {
            "place": [
                "tree/junglebush/3"
            ],
            "chance": 0.1
        }
    ],
    "decorators": [
        {
            "chance": 1,
            "palette": [
                {
                    "block": "dead_bush"
                }
            ]
        }
    ],
    "slab": {
        "palette": [
            {
                "block": "sandstone_slab"
            }
        ]
    },
    "rarity": 1,
    "debugColor": "#AAAAAA",
    "loot": {
        "mode": "ADD",
        "multiplier": 0,
        "tables": [tools1]
    }
}
```

## Settings

### 1 - Name \*

```javascript
"name": "Beach"
```

The name of the region. It is best to keep / make this the same as the name of the file you are editing. This will only be seen when getting the name of the biome with the [what biome command](../../plugin/commands.md#iris-what-biome).

### 2 - Derivative \*

```javascript
"derivative": "BEACH"
```

The type of biome that Minecraft uses for a number of things:

* The name of the biome as seen in the `F3` debug screen.
* The variants of colors in the leaf blocks as made by the client.
* The variants of colors of water in the oceans & rivers \(for example swamp water\)
* The default type of mobs that spawn in the biome unless overridden
* The environment sound effects that you may hear

This can be any vanilla biome.

### 3 - Layers \*

```javascript
"layers": [
    {
        "palette": [
            {
                "block": "sand"
            }
        ]
    },
    {
        "palette": [
            {
                "block": "dirt"
            }
        ],
        "style": {
            "style": "STATIC"
        },
        "minHeight": 2,
        "maxHeight": 3
    }
]
```

Layers dictate the topmost layers of blocks on the surface. They are stacked ontop of eachother. The order in which the block objects are pasted \(the part between the outermost `{` and `}` \), is the order in which they are placed vertically: The sand in the top of the `"layers"` array will spawn on top of the dirt, which is at the bottom.

We will now go over the parameters in each of the layer objects \(elements in the array\):

{% tabs %}
{% tab title="Palette" %}
```javascript
"palette": [
     {
          "block": "sand"
     }
]
```

Here you specify the block type of the layer. You can also specify multiple blocks by adding more in the following fashion:

```javascript
"palette": [
     {
          "block": "sand"
     },
     {
          "block": "sandstone"
     }
]
```
{% endtab %}

{% tab title="Style" %}
```javascript
"style": {
    "style": "STATIC"
}
```

In the optional style object you can specify a noise layer to spawn the overlay blocks with. You can see the different noise options with the [noise command](../../plugin/commands.md#iris-studio-noise).
{% endtab %}

{% tab title="Min- & MaxHeight" %}
```javascript
"minHeight": 2,
"maxHeight": 3
```

The min- and maxHeight specified are the minimal and maximal height of the overlay layer. Note that the noise layer will overwrite the minimal, since it cuts away blocks after these parameters took effect.
{% endtab %}
{% endtabs %}

### 4 - Generators \*

```javascript
"generators": [
    {
        "generator": "vanilla",
        "max": 1,
        "min": -1
    }
]
```

The generators dictate the way the terrain is generated. You can combine multiple generators in one biome, they will then connect to form terrain you want. This is done by adding a second object to the array like this:

```javascript
"generators": [
    {
        "generator": "vanilla",
        "max": 1,
        "min": -1
    },
    {
        "generator": "iris",
        "max": 1,
        "min": -1
    }
]
```

These are the required parameters:

{% tabs %}
{% tab title="Generator" %}
The generator dictates the noise type that generator object uses.

`"vanilla"` is a mimic of the terrain vanilla Minecraft uses, and `"iris"` is a custom noise type we created. You can see the different noise options with the [noise command](../../plugin/commands.md#iris-studio-noise).
{% endtab %}

{% tab title="Min & Max" %}
```javascript
"max": 1,
"min": -1
```

Here you specify the minimal and maximal height relative to the [`"fluidHeight"` in the Dimensions](dimensions.md#5-fluid-height-r). Note that Iris will, even if your `"min"` and `"max"` heights do not overlap with other biomes in the [Land, Sea & Shore Biomes](regions.md#2-land-sea-and-shore-biomes-r), always make the biomes spawn and connect up properly.
{% endtab %}
{% endtabs %}

### 5 - Objects

```javascript
"objects": [
    {
        "place": [
            "tree/junglebush/3"
        ],
        "chance": 0.1
    }
],
```

The objects array contains all objects that can spawn in the world. There are a couple essential parameters to go over:

{% tabs %}
{% tab title="Place" %}
```javascript
"place": [
    "tree/junglebush/3"
]
```

The `"place"` element contains an array of objects. These objects will be placed with the settings your provide in the object \(the curly brackets, not the schematic\), such as the one on the next page, `"chance"`
{% endtab %}

{% tab title="Chance" %}
```javascript
"chance": 0.1
```

The chance is the likelyness of the object to spawn for each suitable location. Making this equal to `1` will make it so that there is a guaranteed chance at spawning on every suitable location.  
Note that there are other options that can add spawning requirements to the object, these can cause the object to never spawn.
{% endtab %}
{% endtabs %}

### 6 - Decorators

```javascript
"decorators": [
    {
        "chance": 1,
        "palette": [
            {
                "block": "dead_bush"
            }
        ]
    }
],
```

Decorators are similar to [Objects ](biomes.md#5-objects)in that they have similar required parameters. The `"chance"` functions the same and they have some corresponding spawning conditions, but Decorations are blocks, rather than schematics. Using decorators you can have dead bushes spawn around the biome, like in the example.

### 7 - Slab

```javascript
"slab": {
    "palette": [
        {
            "block": "sandstone_slab"
        }
    ]
}
```

Slabs are literal slabs on the terrain that will cause a nice curve. Instead of blocky transitions you can have Iris place half slabs automatically. The required parameter is the `"palette"` array, which takes a `"block"`.

### 8 - Rarity

```javascript
"rarity": 1
```

The rarity can make certain biomes more rare. The higher the number, the lower the spawnrate \(the more "rare"\). Ranges from 1 to 512. See this as 100% / `value` chance of spawning for each location.

### 9 - Debug Color

```javascript
"debugColor": "#AAAAAA"
```

The debug color is the color you see used on the pregeneration map while pregenerating. It is regular hexadecimal color, here you can find [a website with a hexidecamal color picker](https://www.w3schools.com/colors/colors_picker.asp).

### 10 - Loot

```javascript
"loot": {
    "mode": "ADD",
    "multiplier": 0,
    "tables": [global-tools]
 }
```

{% tabs %}
{% tab title="Mode" %}
```javascript
"mode": "ADD"
```

What do do with the parent table \(if specified\):

* ADD: Adds items to the parent
* CLEAR: Removes the parent's items if an item is places on that position
* REPLACE:  Replaces items in the parent's table if selected
{% endtab %}

{% tab title="Multiplier" %}
```javascript
"multiplier": 0
```

The multiplier of the loot if the loot check is passed \(directly multiplies the loot by x\)
{% endtab %}

{% tab title="Tables" %}
```javascript
"tables": [global-tools]
```

The array of tables used to pick loot for the chests.
{% endtab %}
{% endtabs %}

## Mastering

If you cannot find the settings you're looking for here, check out the [Biomes Mastering Page](../mastering/biomes/).

