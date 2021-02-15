---
description: >-
  A typical biome file breakdown. This page specifically is going to explain the
  default, parameters. these parameters WILL be covered in the elsewhere the
  same. this is a quick start
---

# Biomes

{% hint style="warning" %}
This page has not yet been updated in accordance with the new structure. Most information should still be valid, but keep this warning in mind.
{% endhint %}

The information below is a variant of the Biome tutorial, and we would recommend that you familiarize yourself with that first. this would then make more sense especially the complexity will become less complex.

#### Parameters:

* **Name** - What is the biome called in-game, filename refers only to what internal schema know
* **Layer** - What blocks makeup the biome floor, and sub-terrain \(_not including caves\)_
* **Objects** - This lists the 'things' that you want to place all over the place _eg: trees, rocks, etc..._
* **Generators** - The way the terrain Height-map is designed
* **Derivative** - This sets the Vanilla Color, Mob spawn, Weather, and some other event

Many of these here will give you a world that 'looks' like a normal world, but Iris is able to give you so much customization that you can have many types of variants that can look otherworldly.

### These are some examples of other uses of the defaults:

{% tabs %}
{% tab title="Mars Cliffs" %}
{% code title="mariainSandCliffs.json" %}
```javascript
{
    "rarity": 3,
    "name": "High Sand Cliffs",
    "derivative": "CRIMSON_FOREST",
    "layers": [
        {
            "palette": [
                {
                    "block": "red_sand"
                },
                {
                    "block": "orange_concrete_powder"
                }
            ],
            "maxHeight": 2,
            "minHeight": 1,
            "style": {
                "style": "STATIC",
                "zoom": 0.0135
            }
        }
    ],
    "generators": [
        {
            "generator": "sands-cliffs",
            "min": 112,
            "max": 220
        }
    ]
}
```
{% endcode %}
{% endtab %}

{% tab title="Nether" %}
{% code title="nether.json" %}
```javascript
{
    "name": "Nether Wastes",
    "derivative": "NETHER_WASTES",
    "layers": [
        {
            "palette": [
                {
                    "block": "netherrack"
                }
            ],
            "style": {
                "style": "FLAT"
            }
        }
    ],
    "generators": [
        {
            "generator": "hell",
            "min": 141,
            "max": 186
        }
    ]
}
```
{% endcode %}
{% endtab %}

{% tab title="Vanilla Swamp" %}
{% code title="swamp-forest.json" %}
```javascript
{
    "name": "Swamp Forest",
    "derivative": "SWAMP",
    "rarity": 4,
    "layers": [
        {
            "palette": [
                {
                    "block": "grass_block"
                }
            ]
        },
        {
            "palette": [

                {
                    "block": "dirt"
                }
            ],
            "maxHeight": 3,
            "minHeight": 2
        }
    ],
    "objects": [
        {
            "place": [
                "tree/swamp/1",
                "tree/swamp/2",
                "tree/swamp/3",
                "tree/swamp/4",
                "tree/swamp/5"
            ],
            "translate": {
                "y": 1
            },
            "chance": 1,
            "density": 3
        }
    ],
    "generators": [
        {
            "generator": "vanilla",
            "max": 4,
            "min": -1
        }
    ]
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

### Recap:

Much of what you have seen above, IS used in the example projects, when it comes to what a final project biome looks like, they would look like something like this

{% tabs %}
{% tab title="Frozen Pines" %}
```javascript
{
    "biomeSkyScatter": [
        "SNOWY_TAIGA",
        "SNOWY_MOUNTAINS"
    ],
    "objects": [
        {
            "chance": 0.02,
            "density": 3,
            "snow": 0.35,
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
                "ice-spikes/ic-1",
                "ice-spikes/ic-2"
            ],
            "translate": {
                "x": 0,
                "y": 0,
                "z": 0
            }
        },
        {
            "chance": 0.8,
            "snow": 1,
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
                "evergreen/fantasy_evergreen_large1",
                "evergreen/fantasy_evergreen_large1"
            ],
            "translate": {
                "x": 0,
                "y": -2,
                "z": 0
            }
        },
        {
            "chance": 0.05,
            "density": 3,
            "snow": 0.35,
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
                "ice-spikes/ice-spec-1",
                "ice-spikes/ice-spec-2"
            ],
            "translate": {
                "x": 0,
                "y": 0,
                "z": 0
            }
        }
    ],
    "biomeZoom": 30,
    "derivative": "SNOWY_TAIGA_MOUNTAINS",
    "biomeStyle": {
        "style": "IRIS"
    },
    "decorators": [
        {
            "chance": 1,
            "variance": {
                "style": "IRIS",
                "zoom": 0.25
            },
            "palette": [
                {
                    "data": {
                        "layers": 1
                    },
                    "block": "snow"
                },
                {
                    "data": {
                        "layers": 2
                    },
                    "block": "snow"
                },
                {
                    "data": {
                        "layers": 3
                    },
                    "block": "snow"
                },
                {
                    "data": {
                        "layers": 4
                    },
                    "block": "snow"
                }
            ]
        }
    ],
    "children": [
        "frozen-vander"
    ],
    "name": "Frozen Pines",
    "layers": [
        {
            "minHeight": 2,
            "maxHeight": 3,
            "palette": [
                {
                    "block": "snow_block"
                }
            ]
        },
        {
            "minHeight": 2,
            "maxHeight": 4,
            "palette": [
                {
                    "block": "packed_ice"
                }
            ]
        },
        {
            "minHeight": 6,
            "maxHeight": 18,
            "style": {
                "style": "STATIC"
            },
            "palette": [
                {
                    "block": "stone"
                },
                {
                    "block": "andesite"
                },
                {
                    "block": "stone"
                }
            ]
        }
    ],
    "generators": [
        {
            "min": 3,
            "max": 16,
            "generator": "plain"
        },
        {
            "min": 13,
            "max": 48,
            "generator": "mountain"
        }
    ],
    "childShrinkFactor": 20,
    "wall": {
        "style": {
            "style": "STATIC"
        },
        "palette": [
            {
                "block": "stone"
            },
            {
                "block": "andesite"
            },
            {
                "block": "stone"
            }
        ]
    },
    "biomeScatter": [
        "SNOWY_TAIGA_MOUNTAINS",
        "TAIGA_HILLS",
        "MOUNTAINS",
        "ICE_SPIKES"
    ]
}
```
{% endtab %}
{% endtabs %}

## Post Overview

We highly recommend that you familiarize yourself, and toy around with them before diving straight into the heavy lifting- that is, advanced biome manipulation. Biomes are the some of the most important parts of this plugin. I don't think i need to explain how important that the biomes are, please familiarize yourself with Vs-code and make a custom biome using \[[this](../../understanding/biomes.md)\] to do so; once you do that feel free to dive into the harder parts in the next page. Good luck, we hope that you make a world of your dreams.

