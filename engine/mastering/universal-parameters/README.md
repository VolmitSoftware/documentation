---
description: >-
  This page is to explain parameters that are not unique to each file. For
  example, this can have information for Regions, that can also be in
  Dimensions, or Biomes.
---

# Universal Parameters

### What's Covered Here:

* **Style**
* **Blocks**
* **Drops**
* **Deposits**
* **Loot**
* **Palette**
* **Slope**
* **Generator**
* **Objects \(too many options!\)**
* **Text**
* **Rarity**
* **Regions**

## Style/Generator Breakdown

{% tabs %}
{% tab title="Style" %}
```javascript
    "......Style": {
        "exponent": 1,
        "fracture": {},
        "multiplier": 1,
        "style": "IRIS",
        "zoom": 1
    },
```
{% endtab %}

{% tab title="Style Fractured" %}
```javascript
    "caveBiomeStyle": {
        "exponent": 1,
        "fracture": {
            "exponent": 1,
            "fracture": {},
            "multiplier": 0.2,
            "style": "IRIS",
            "zoom": 0.5
        },
        "multiplier": 1,
        "style": "IRIS",
        "zoom": 1
    },
```
{% endtab %}

{% tab title="Style Over-Fractured" %}
```javascript
//You can litterally fracture forever for infinite possible solutions... This is a joke page
        "caveBiomeStyle": {
        "exponent": 1,
        "fracture": {
            "exponent": 1,
            "fracture": {
                "exponent": 0
                "fracture": {
                    "exponent": 0
                    "fracture": {
                        "exponent": 0
                        "fracture": {
                            "exponent": 0
                            "fracture": {}
                            "multiplier": 0
                            "style": ""
                            "zoom": 0
                        }
                        "multiplier": 0
                        "style": ""
                        "zoom": 0
                    }
                    "multiplier": 0
                    "style": ""
                    "zoom": 0
                }
                "multiplier": 0
                "style": ""
                "zoom": 0
            },
            "multiplier": 0.2,
            "style": "IRIS",
            "zoom": 0.5
        },
        "multiplier": 1,
        "style": "IRIS",
        "zoom": 1
    },
```
{% endtab %}
{% endtabs %}

#### Style/Generator Explained:

Style/Generator is the 4-D _\(that's one more D than 3D\)_ rules that draw the carve layer. **Static** is a commonly used style, with any multiplier, or zoom- it is easy noise. **IRIS,** is our home-brewed Style that we use in places all over the Overworld

<table>
  <thead>
    <tr>
      <th style="text-align:left">Exponent</th>
      <th style="text-align:left">Fracture</th>
      <th style="text-align:left">Multiplier</th>
      <th style="text-align:left">Style</th>
      <th style="text-align:left">Zoom</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p><em>Max: </em><b>64</b>
        </p>
        <p><em>Min:  </em><b>0.01562</b>
        </p>
        <p>Exponent to the Multiplier.</p>
      </td>
      <td style="text-align:left">This Distorts the Parent Gen/Style With this.</td>
      <td style="text-align:left">The Output Multiplier (use only if this is not the Parent).</td>
      <td style="text-align:left">Type of noise, Many to pick from.</td>
      <td style="text-align:left">The zoom in, or out of the style.</td>
    </tr>
  </tbody>
</table>

## Blocks Breakdown

{% tabs %}
{% tab title="Blocks" %}
```javascript
"blocks": [{
        "backup": {},
        "block": "acacia_button",
        "data": {}
        "debug": false,
        "key": ""
        "weight": 0
    }]
```
{% endtab %}

{% tab title="Blocks Demo" %}
```javascript
"blocks": [
    {
            //you can have this go infinite
            "backup": {"block": "oak_button"},
            "block": "acacia_button",
            "data": {"watterlogged": true},
            "debug": false,
            "key": "minecraft",
            "weight": 1
    }
 ]
```
{% endtab %}
{% endtabs %}

#### Blocks Explained:

Style is the 4-D _\(that's one more D than 3D\)_ rules that draw the carve layer. **Static** is a commonly used style, with any multiplier, or zoom- it is easy noise. **IRIS,** is our home-brewed Style that we use in places all over the Overworld

| Backup | Data | Debug | Key | Weight |
| :--- | :--- | :--- | :--- | :--- |
| You put \[block\] here, its just a replacement | Optional Data, Such as Water-logging | Print to the console when a block is replaced \[Bool\] | The Resource Key, usually Minecraft text | If this is a part of a list, how many times will this be considered |

## Drops Breakdown

{% tabs %}
{% tab title="Drops" %}
```javascript
"drops": [
        {
            "attributes": [],
            "customModel": "",
            "displayName": "",
            "dyeColor": "BLACK",
            "enchantments": [],
            "itemFlags": [],
            "leatherColor": "",
            "lore": [],
            "maxAmount": 0,
            "maxDurability": 0,
            "minAmount": 0,
            "minDurability": 0,
            "rarity": 0,
            "slotTypes": "",
            "type": "acacia_boat",
            "unbreakable": false
        }
    ]
```
{% endtab %}

{% tab title="Drops Demo" %}
```javascript

```
{% endtab %}
{% endtabs %}

#### Drops Explained:

Drops are the **items** that are dropped when broken, or are tossed into chests as **loot**. If you were linked here, that means the things here are referenced in whatever module you are looking into

| Attributes | Custom Model | Display Name | Dye Color | Enchantments |
| :--- | :--- | :--- | :--- | :--- |
| This applies attribute modifiers to the item | Custom Model Identifier \[**1.14+**\] int-Id | In-game Name of this item | If color-able, What color | Applies an enchant to this item |

| Item Flags | Leather Color | Lore | Max Amount | Max Durability |
| :--- | :--- | :--- | :--- | :--- |
| Adds Flags to items, no limit. | If Leather, What color, default empty | String of text that is the in-game description | How many Max stack, default 1 | If has Durability, what is maximum |

| Min Amount | Min Durability | Rarity | Slot Types | Type |
| :--- | :--- | :--- | :--- | :--- |
| Minimum amount that can drop | If has Durability, what is minimum | The sub rarity of loot **POST** loot table roll | STORAGE, is what you are looking for usually. others are available | The Type of item, if it were to be included in a sub-menu: **DIAMOND\_SWORD**, or **DIRT**, etc... |

| Unbreakable |
| :--- |
| Boolean for if the item is unbreakable. The reader of this is Unbreakable ♥ |

## Deposits Breakdown

{% tabs %}
{% tab title="Deposits " %}
```javascript
"deposits": [
    {
        "maxHeight": 0,
        "maxPerChunk": 0,
        "maxSize": 0,
        "minHeight": 0,
        
        "minPerChunk": 0,
        "minSize": 0,
        "palette": [{}],
        "varience": 0,
    }
],
```
{% endtab %}

{% tab title="Deposits Demo" %}
```javascript
"deposits": [
    {
        "maxHeight": 0,
        "maxPerChunk": 1,
        "maxSize": 1,
        "minHeight": 0,
        "minPerChunk": 0,
        "minSize": 1,
        "palette": [
            {
                "backup": {"block":"lapis_ore"},
                "block": "gold_ore",
                "data": {},
                "debug": false,
                "key": "",
                "weight": 1
            }
        ],
        "varience": 3
    }
],
```
{% endtab %}
{% endtabs %}

#### Deposits Explained:

Deposits are the ores, or clumps of stuff that is spawned in the ground. like Dirt patches, or Ores. This is a great way to set ores, This also supports custom blocks- Using the palette you can have whatever spawn, from custom blocks to doors can be deposits. This can be set in the Dimension, Region, and Biome.

| Max Height | Max Per Chunk | Max Size | Min Height |
| :--- | :--- | :--- | :--- |
| The Maximum Height the Deposit can generate | The Maximum 'Clumps' that can be spawned in a chunk | Max blocks in the clump | The Minimum Height the Deposit can generate |

| Min Per Chunk | Min Size | Palette | Variance |
| :--- | :--- | :--- | :--- |
| The Minimum 'Clumps' that can be spawned in a chunk | Min blocks in the clump | This in itself is a universal Parameter, learn about it \[[Here](./#palette-breakdown)\] | How many different object shapes will be generated. Max is 64 |

## Palette Breakdown

{% tabs %}
{% tab title="Palette" %}
```javascript
"palette": [
       {
                "backup": {"block":"lapis_ore"},
                "block": "gold_ore",
                "data": {},
                "debug": false,
                "key": "",
                "weight": 1
       }
  ],
```
{% endtab %}

{% tab title="Palette Demo" %}
```javascript
"palette": [
    {
    "backup": {"block":"lapis_ore"},
    "block": "gold_ore",
    "data": {},
    "debug": false,
    "key": "",
    "weight": 1
    }
],
```
{% endtab %}
{% endtabs %}

#### Palette Explained:

The palette is the set of blocks that are included in the parent function's list of parameters. you can have as many as you want as long as everything is properly labeled.

| Backup | Block | Data |
| :--- | :--- | :--- |
| In the event that the block cant be placed in this version of MC, the backup is a palette of alternatives.  | This can have as many blocks as you want | Extra block data, like Waterlogged, or Count etc |

| Debug | Key | Weight |
| :--- | :--- | :--- |
| This prints to the console whenever this block is placed, or whenever the palette rolls. | This is the resource key- leave blank unless you are using a pack | The number of this block in a hypothetical random list. more = better chance |

## Fluid Breakdown

{% tabs %}
{% tab title="Palette" %}
```javascript
    "fluid": {
        "fluidHeight": 0,
        "fluidType": {},
        "inverseHeight": false
    },
```
{% endtab %}

{% tab title="Palette Demo" %}
```javascript
// lava below 15    
    "fluid": {
        "fluidHeight": 15,
        "fluidType": {"block": "lava"},
        "inverseHeight": false
    },
```
{% endtab %}
{% endtabs %}

#### Fluid Explained:

Fluid layers are a simple way to set a sort of water-layer or anything-layer in the parent. upi can put blocks here, but its built for fluids.

| Fluid-Height | Fluid Type | Inverse Height |
| :--- | :--- | :--- |
| The layer and below that in the parent that this block will propagate   | This is a palette layout. To learn how to use a palette go [here](./#palette-breakdown) | Inverts the Fluid-Height, if its 15, and this is inverted so its everything above 15. |

## Slope Breakdown

{% tabs %}
{% tab title="Slope" %}
```javascript
 "Slope": {
   "generator": {},
   "max": 0,
   "min": 0
 }
```
{% endtab %}
{% endtabs %}

#### Slope Explained:

Slope is the generator that determines the direction/form of the parent function.

| Generator | Min | Max |
| :--- | :--- | :--- |
| This is an essential Fork of Style, and allows for Fracturing Learn how to use it [here](./#style-generator-explained) | Min block level in the slope | Max block level in the slope |

## Loot Breakdown

{% tabs %}
{% tab title="Loot" %}
```javascript
    "loot": {
        "mode": "",
        "multiplier": 0,
        "tables": []
     },
```
{% endtab %}

{% tab title="Loot Demo" %}
```javascript
    "loot": {
        "mode": "ADD",
        "multiplier": 0,
        "tables": [global-tools]
     },
```
{% endtab %}

{% tab title="Example Loot File" %}
{% code title="global-tools.json" %}
```javascript
// Example Loot File
{
    "name": "Global Tools",
    "rarity": 1,
    "maxPicked": 1,
    "loot": [
        {
            "type": "WOODEN_PICKAXE",
            "maxAmount": 1,
            "rarity": 5,
            "minDurability": 0.2,
            "maxDurability": 0.8,
            "slotTypes": "STORAGE"
        },
        {
            "type": "FLINT_AND_STEEL",
            "maxAmount": 1,
            "rarity": 5,
            "minDurability": 0.2,
            "maxDurability": 0.8,
            "slotTypes": "STORAGE"
        }
        ,{
            "type": "SHEARS",
            "maxAmount": 1,
            "rarity": 7,
            "minDurability": 0.2,
            "maxDurability": 0.8,
            "slotTypes": "STORAGE"
        },
        {
            "type": "BOW",
            "maxAmount": 1,
            "rarity": 8,
            "minDurability": 0.4,
            "maxDurability": 0.8,
            "slotTypes": "STORAGE"
        }
    ]
}
```
{% endcode %}
{% endtab %}
{% endtabs %}

#### Loot Explained:

Slope is the generator that determines the direction/form of the parent function.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Mode</th>
      <th style="text-align:left">Multiplier</th>
      <th style="text-align:left">Tables</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">
        <p>What to do with the parent table (if any)</p>
        <p>ADD, CLEAR, REPLACE</p>
      </td>
      <td style="text-align:left">Multiplier for the loot if loot check is passed.</td>
      <td style="text-align:left">The loot tables that will be included in the parent&apos;s loot drop</td>
    </tr>
  </tbody>
</table>

## Objects Breakdown

{% tabs %}
{% tab title="Objects " %}
```javascript
"objects": [{
                "boarExtendMaxY": 0,
                "boarExtendMinY": 0,
                "bore": false,
                "bottom": false,

                "carvingSupport": "",
                "chance": 0,
                "clamp": {},
                "density": 0,

                "edit": [],
                "meld": false,
                "mode": "",
                "onwater": false,

                "overStilt": 0,
                "place": [],
                "rotation": {},
                "smartBore": false,

                "snow": 0,
                "translate": {},
                "translateCenter": false,
                "underwater": false,

                "warp": {},
                "waterloggable": false,

            }]
        }
```
{% endtab %}

{% tab title="Objects Demo" %}
```javascript
    "objects": [
        {
            "chance": 0.03,
            "density": 3,
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
                "wonderland/wonder-1",
                "wonderland/wonder-2",
                "wonderland/wonder-3"
            ],
            "translate": {
                "x": 0,
                "y": -5,
                "z": 0
            }
        },
```
{% endtab %}
{% endtabs %}

#### Objects Explained:

Objects have loads of edits, and things you can do with them. \(Psycho caused this\) but this is one of the biggest, if not the biggest set of information and toggles that you can do.

| Boar Extend MaxY | Boar Extend MinY | Bore | Bottom |
| :--- | :--- | :--- | :--- |
| Assuming Bore is enabled, this will expand the bore Height Cuboid range by \[num\] | Assuming Bore is enabled, this will expand the bore Width Cuboid range by \[num\] | A bool as to if on placement of an object, will it erase everything in a cube around this object | If set to true, this object will place from the ground up instead of height checks when not y locked to the surface. **This is not compatible with X and Z axis rotations \(it may look off\)** |

| Carving Support | Chance | Clamp | Density |
| :--- | :--- | :--- | :--- |
| This object can place ANYWHERE, CARVING\_ONLY or SURFACE\_ONLY, all of the objects interact with carving how you would expect. | The chance for this to place in a chunk. **If you need multiple per chunk, set this to 1 and use density.** | Limit the Max height or min height of a placement  of an object | If the check passes. this number of an object will place in a chunk |

| Edit | Meld | Mode | On-Water |
| :--- | :--- | :--- | :--- |
| This is the module where you find and replace blocks in the objects. | If set to true, this object will only place parts of itself where blocks already exist. **Warning: Melding is very performance intensive!** | This is the mode pf placement. See placement modes here. | A boolean that determines if it places on water. |

| Over Stilt | Place | Rotation | Smart Bore |
| :--- | :--- | :--- | :--- |
| When the place mode is set to STILT, this will stilt 1-3 blocks into the ground additionally | This is just a list of objects to place | If this object will receive a random rotation degree, if so, what degree | If set to true, Iris will try to fill the insides of 'rooms' and 'pockets' where air should fit based off of **Ray-Tracing** \(Yea We have RTX on\) checks. This prevents a village house placing in an area where a tree already exists, and instead replaces the parts of the tree where the interior of the structure is. |

| Snow | Translate | Translate Center | Underwater |
| :--- | :--- | :--- | :--- |
| This is percentage \(0-1\) of the amount of a snow filter that puts a snow stacks on a block | On an X, Y, and Z Coordinate plane, this moves an object on placement | If the place mode is set to CENTER\_HEIGHT\_RIGID and you have an X/Z translation, Turning on translate center will also translate the center height check. | If set to true, objects will place on the terrain height, ignoring the water surface. |

| Warp | WaterLoggable |
| :--- | :--- |
| This is an interesting one, you will need to use a generator to warp the field of coordinates. Using simplex for example would make a square placement warp like a flag | If set to true, Blocks placed underwater that could be waterlogged are waterlogged |

## Text

**Place text all over the terrain, literally.**  
Text can actually be printed all over the ground, see this [image](https://media.discordapp.net/attachments/315541537155186688/747770260479934524/2020-08-25_06.51.24.png?width=1275&height=682) it's able to print with specific fonts as well, see all the info below

| Chance | Clamp | Density | Mode | Water-Loggable |
| :--- | :--- | :--- | :--- | :--- |
| Chance to place this text per chunk | The clamp Height for this text if any. | The amount of times to print this, if the chance pass, per chunk. | See Mode in SubParameters | Boolean as to if the text should be waterlogged |

| On Water | Render | Rotation | translate | Underwater |
| :--- | :--- | :--- | :--- | :--- |
| Can it place on water regions or not. ie: if an area is labeled as ocean, even on an edge it cant place here if toggled off | This is the style of text printed, See render | If this object will receive a random rotation degree, if so, what degree | On an X, Y, and Z Coordinate plane, this moves an object on placement | Boolean to see if this ever places underwater. |

## Rarity

**The rarity of this biome \(integer\)**  
Generally speaking the higher the number is, the more common it is, but if you have only a few biomes try to keep the results as you would want, try and keep it under 256 \(you can go higher\), but higher would make the biome almost invisible in a general schema of 100 biomes, as every biome \(and region\) is a roll at random EACH usage so if its 1-in-10, there will NOT guarantee a biome every 10, as its a random roll.

## Effects \*

**Effects that play in this biome.**  
Effects are ambient effects such as potion effects, random sounds, or even particles around each player. All of these effects are played via packets so two players won't see/hear each others effects. Due to performance reasons, effects will play aground the player even if where the effect was played is no longer in the biome the player is in.

