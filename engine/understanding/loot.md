---
description: This page will go over Basics in Loot
---

# Loot

## Topics

1. [Video Tutorial](loot.md#video-tutorial)
2. [Introduction](loot.md#introduction)
3. [Default in the example](loot.md#default-in-the-example)
4. [General Explanation](loot.md#general-explanation)
5. [Settings](loot.md#settings)
   1. [Name \*](loot.md#1-name)
   2. [Loot \*](loot.md#2-loot)
   3. [Min- & MaxPicked](loot.md#3-min-and-maxpicked)
   4. [Rarity](loot.md#4-rarity)

{% hint style="info" %}
Every setting with a `*` is mandatory for this file
{% endhint %}

## Video Tutorial

> To be added later

## Introduction

Loot are `json` files and they are placed in the `loot` folder. Loot tables can be referenced when defining loot in different dimensions, biomes, regions and even structures. They decide which items spawn in the chests they are assigned to.

{% hint style="info" %}
Note that loottables are somewhat sensitive and can quite easily be broken by, for example, placing the minimal amount of items higher than the maximal amount the chest can actually hold.

Make sure the settings you make are possible beforehand.
{% endhint %}

{% hint style="success" %}
Check out [Loot in Biomes](biomes.md#10-loot) to add the loot table you configure using this page to biomes.
{% endhint %}

## Default in the example

The Loot file is called `loot1.json` and can be found in the `loot` folder:

```javascript
{
    "name": "loot1",
    "loot": [
        {
            "type": "wooden_sword",
            "rarity": 3,
            "slotTypes": "STORAGE"
            "minAmount": 1,
            "maxAmount": 3,
            "displayName": "Le Slap",
            "enchantments": [
                {
                    "enchantment": "KNOCKBACK",
                    "chance": 0.2,
                    "minLevel": 1,
                    "maxLevel": 2
                }
            ],
        },
        {
            "type": "fishing_rod",
            "rarity": 11,
            "slotTypes": "STORAGE"
            "maxAmount": 1,
            "minDurability": 0.5,
        },
        {
            "type": "sugar",
            "rarity": 4,
            "slotTypes": "STORAGE"
            "maxAmount": 3,
        }
    ]
    "minPicked": 3,
    "maxPicked": 30,
    "rarity": 2
}
```

## General Explanation

Loot tables have many different RNG based rolls.

1. [Rarity in the table](loot.md#4-rarity)
2. [Rarity in the item](loot.md#2-loot)

&lt;todo&gt;

## Settings

### 1 - Name \*

```javascript
"name": "loot1"
```

This is the name of the loot table which does not affect anything other than the result of getting area information with the [Statistics command](../../plugin/commands.md#ir-metrics-stats-mt).

{% hint style="info" %}
To make sure you don't confuse yourself or Iris, name this the exact same as the file name.
{% endhint %}

### 2 - Loot \*

```javascript
"loot": [
    {
        "type": "wooden_sword",
        "rarity": 3,
        "slotTypes": "STORAGE"
        "minAmount": 1,
        "maxAmount": 3,
        "displayName": "Le Slap",
        "enchantments": [
            {
                "enchantment": "KNOCKBACK",
                "chance": 0.2,
                "minLevel": 1,
                "maxLevel": 2
            }
        ],
    },
    {
        "type": "fishing_rod",
        "rarity": 11,
        "slotTypes": "STORAGE"
        "maxAmount": 1,
        "minDurability": 0.5,
    },
    {
        "type": "sugar",
        "rarity": 4,
        "slotTypes": "STORAGE"
        "maxAmount": 3,
    }
]
```

The loot array contains all types of loot that can spawn using this loot configuration.

Each element contains the following:

{% tabs %}
{% tab title="Type\*" %}
```javascript
"type": "wooden_sword"
```

The item
{% endtab %}

{% tab title="Rarity\*" %}
```javascript
"rarity": 3
```

The chance this item is picked on each iteration. Always 1 / x chance **if this element is picked**.
{% endtab %}

{% tab title="SlotType\*" %}
```javascript
"slotTypes": "STORAGE"
```

The type of the slot the item can spawn in.  
Types:

1. `STORAGE` Most used, simple slot like in a chest, barrel, etc.
2. `FUEL` Fuel slot of any type of furnace
3. `FURNACE` Furnace slot of a normal furnace
4. `SMOKER`Furnace slot of a smoker
5. `BLAST_FURNACE`Furnace slot of a blast furnace
{% endtab %}

{% tab title="Min- & MaxAmount" %}
```javascript
"minAmount": 1,
"maxAmount": 3
```

Respectively the minimal and maximal boundary on the amount of this type of item that is / are picked
{% endtab %}

{% tab title="DisplayName" %}
```javascript
"displayName": "Le Slap"
```

The name of the item
{% endtab %}

{% tab title="Enchantments" %}
```javascript
"enchantments": [
    {
        "enchantment": "KNOCKBACK",
        "chance": 0.2,
        "minLevel": 1,
        "maxLevel": 2
    }
]
```

The \(possible\)  enchantments applied to the item.

{% hint style="info" %}
This should only work on items that can actually get that enchantment but that may not always be the case.
{% endhint %}

| Option | Setting | Effect |
| :--- | :--- | :--- |
| "enchantment": |  "KNOCKBACK" | Applied enchantment |
| "chance": | 0.2 | Chance of application |
| "minLevel":  | 1 | Minimal level |
| "maxLevel": | 2 | Maximal level |

Note that the minimal and maximal level are equally distributing all levels inbetween and including themselves after chance is picked. This means that _if_ the enchantment is applied, the chance of _all levels of the enchantment_ is equal.
{% endtab %}
{% endtabs %}

There are far more settings under loot which do stuff like add lore, durability and more. All these settings \(with a short explanation, hopefully\) are findable with the ctrl + space keycombination in VSCode.

### 3 - Min- & MaxPicked

```javascript
"minPicked": 3,
"maxPicked": 30
```

Respectively the minimal and maximal boundary on the amount of times this loot tree that is picked

### 4 - Rarity

```javascript
"rarity": 2
```

The overall chance a container this loot table is assigned to gets loot from this. This is absolute chance, meaning if this random roll fails, nothing will come from this table.

## Mastering

If you cannot find the settings you're looking for here, check out the [Template Mastering Page]()

