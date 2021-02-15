---
description: This page will go over Basics in Generators
---

# Generators

## Topics

1. Video Tutorial
2. Introduction
3. Default in the example
4. Settings
   1. Interpolator \*
   2. Seed \*
   3. Composite \*
   4. Setting
   5. Setting
   6. Setting
   7. Setting
   8. Setting
   9. Setting

{% hint style="info" %}
Every setting with a `*` is mandatory for this file
{% endhint %}

## Video Tutorial

> To be added later

## Introduction

Generators are `json` files and they are placed in the `generators` folder. Generators are Noise Generators. Noise generators take a coordinate x,z or x,y,z and convert it into a height value. You can explore different base noise styles by using the [studio noise command](../../plugin/commands.md#iris-studio-noise). Generators can take multiple noise styles with additional options and are used to decide the shape of your terrain.

## Default in the example

The Generator file is called `generator.json` and can be found in the `generators` folder:

```javascript
{
    "interpolator": {
        "function": "BILINEAR_STARCAST_9",
        "horizontalScale": 41
    },
    "seed": 12345,
    "composite": [
        {
            "style": {
                "style": "IRIS",
                "zoom": 0.87,
                "fracture": {
                    "style": "IRIS_HALF",
                    "zoom": 0.295,
                    "multiplier": 18
                },
                "exponent": 1.125
            },
            "seed": 54321,
            "bezier": true,
            "exponent": 1.125
        }
    ]
}
```

## Settings

### 1 - Interpolator \*

```javascript
"interpolator": {
    "function": "BILINEAR_STARCAST_9",
    "horizontalScale": 41
}
```

The interpolator describes the way Iris connects this biome to another. It is the way this biome is placed inside the other biome. Below is a screenshot of an example of a more radical version where, as you can see, the mountain biome is being placed into the beach / desert biome.

![](../../.gitbook/assets/image%20%282%29.png)

The interpolator uses two settings which must both be specified:

{% tabs %}
{% tab title="Function \*" %}
```javascript
"function": "BILINEAR_STARCAST_9"
```

This is where you specify the type of function used in the transition. These are not normal noise functions as they do very different things. We recommend the Bilinear Starcast 9 since it gives nice transitions. You can read more about these functions by hovering your mouse over the one specified.
{% endtab %}

{% tab title="Horizontal Scale \*" %}
```javascript
"horizontalScale": 41
```

The horisontal scale indicates the size of the checked range. The larger this is, the smoother, the smaller this is, the more detail.
{% endtab %}
{% endtabs %}

### 2 - Seed \*

```javascript
"seed": 12345
```

The seed is a number you can pick which randomises the algorithms behind the functions. Changing this value may lead to completely different outcomes, but never predictably so. 

### 3 - Composite \*

```javascript
"composite": [
    {
        "style": {
            "style": "IRIS",
            "zoom": 0.87,
            "fracture": {
                "style": "IRIS_HALF",
                "zoom": 0.295,
                "multiplier": 18
            },
            "exponent": 1.125
        },
        "seed": 54321,
        "bezier": true,
        "exponent": 1.125
    }
]
```

The composite is the main generator of the biome this generator is used for. We again see seed, which functions similarly to the previously explained [Seed](generators.md#2-seed) and will not be handled here again.

This function can completely change the way your terrain looks, from very spiky to smooth. Note that this does not affect the height of the terrain, this is done in the [Biome under Generator](biomes.md#4-generators).

**Style**

The style is the actual noise configuration for this generator. This has the greatest influence on the terrain.

```javascript
"style": {
    "style": "IRIS",
    "zoom": 0.87,
    "fracture": {
        "style": "IRIS_HALF",
        "zoom": 0.295,
        "multiplier": 18
    },
    "exponent": 1.125
}
```

{% tabs %}
{% tab title="Style \*" %}
```javascript
"style": "IRIS"
```

The style is the noise algorithm for this noise layer. It has all the noises found in the [Studio Noise GUI](../../plugin/commands.md#iris-studio-noise) and directly influences height for the terrain. You can get more information on the algorithm by hovering over the entered one.
{% endtab %}

{% tab title="Zoom" %}
```javascript
"zoom": 0.87
```

The zoom quite literally zooms in and out on the specified noise. If you feel like the biome is too smooth, for example, you can make this number lower so it zooms out, giving more detail in the terrain. Making this higher achieves the opposite, a smoother terrain.
{% endtab %}

{% tab title="Fracture" %}
```javascript
"fracture": {
    "style": "IRIS_HALF",
    "zoom": 0.295,
    "multiplier": 18
}
```

The fracture is an additional noise object which distorts the input coordinates for the style or, if there is another fracture in the fracture \(which you can indeed stack\), for the parent fracture. This can make for more natural looking terrain, but it can also make it look more randomized \(which is not usually natural. It takes the same parameters as the Style object we are already editing.
{% endtab %}

{% tab title="Exponent" %}
```java
"exponent": 1.125
```

The exponent is a power on the noise. Making this higher will result in more spiky terrain with less noticeable detail. Making this too low will make the area flat and can cause generation errors.
{% endtab %}
{% endtabs %}

**Other**

{% tabs %}
{% tab title="Bezier" %}
```javascript
"bezier": true
```

The Bezier curve is a curve used in computing graphics for making circular / curved lines more smooth. Keeping this on will make the curves of the terrain more smooth. Turning it off will make terrain more spiky.
{% endtab %}

{% tab title="Exponent" %}
```javascript
"exponent": 1.125
```

This functions the same way as the exponent in the Style but it affects terrain slope instead of terrain detail.
{% endtab %}
{% endtabs %}

### 4 - Setting

```javascript
"Setting": value
```

Explanation

### 5 - Setting

```javascript
"Setting": value
```

Explanation

### 6 - Setting

```javascript
"Setting": value
```

Explanation

### 7 - Setting

```javascript
"Setting": value
```

Explanation

### 8 - Setting

```javascript
"Setting": value
```

Explanation

### 9 - Setting

```javascript
"Setting": value
```

Explanation

## Mastering

If you cannot find the settings you're looking for here, check out the [Template Mastering Page]()

