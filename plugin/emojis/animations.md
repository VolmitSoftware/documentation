---
description: >-
  Gloss offers highly efficient animations for use on holograms, boards, and the
  tablist
---

# Animations

## Understanding Animations

Gloss animations are symmetrical. This means that you add "frames" of text and set a framerate. Every frame in the animation will animate under the specified framerate. This allows gloss to produce very high or fine tuned framerates without the need of actually ticking them.

### Creating Animations

```javascript
{
    "target-framerate": 2,
    "frames": [
        "1",
        "2",
        "3",
        "4",
        "5",
        "6",
        "7",
        "8",
        "9"
    ],
    "animation-type": "ASCEND"
}
```

Our frame rate is set to 2. This means the animation will switch frames 2 times a second.

Our animation type is set to `ASCEND` This means gloss will start at 1, and move down the list to `9` then wrap back around to `1` .

### Animation Types

Assume the sequence is `ONE` `TWO` `THREE` .

{% tabs %}
{% tab title="ASCEND" %}
Ascend moves down the list, then jumps back to the top

* ONE
* TWO
* THREE
* ONE
* TWO
* THREE
* ...
{% endtab %}

{% tab title="DESCEND" %}
Descend moves up the list from the bottom and wraps back to the bottom after it reaches the top of the list.

* THREE
* TWO
* ONE
* THREE
* TWO
* ONE
* ...
{% endtab %}

{% tab title="ASCEND\_DESCEND" %}
Starts at the top and moves down the list to the bottom, then moves back to the top.

* ONE
* TWO
* THREE
* TWO
* ONE
* TWO
* THREE
* ...
{% endtab %}

{% tab title="RANDOM" %}
Randomly selects a frame and displays it. Has a chance to display the same frame multiple times in a row if there is not enough frames.

* ONE
* THREE
* TWO
* ONE
* THREE
* ONE
* ...
{% endtab %}
{% endtabs %}

### Using Animations

You can use animations by calling them through a function in gloss `|animation.<name>|`

So, if you create an animation `count.json` then you would use it in a hologram with `|animation.count|` .

Interestingly, if you have the count animation using numbers, you can feed it into an emoji. Gloss comes with the circled number emojis used by `:1:` `:2:` and so on. You can plug the animation into an emoji like so `:|animation.count|:` This will change the emoji called. However it may be simpler to just specify emojis in the animation frames manually.

