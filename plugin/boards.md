---
description: >-
  Boards (scoreboards) in gloss are a powerful way to display information to
  players wherever they are
---

# Boards

## Working with Multiple Boards

Gloss does not make use of a single board. You can create as many boards as you like, and configure each one differently. You can define group specific boards and more.

The base command for boards is **/board**

### Creating Boards

To create a board, simply use:

{% hint style="success" %}
/board new &lt;name&gt;
{% endhint %}

![](../.gitbook/assets/image%20%284%29.png)

### Editing Boards

Gloss boards are located in gloss's data folder **Gloss/boards/&lt;name&gt;.json.** Changes auto-load into the boards. No need to reload.

### Board Defaulting

If you only need a single board for everyone, you can set the board to the default board show it is shown whenever you log in or change worlds. Everyone will see this board.

{% hint style="success" %}
/board default &lt;name&gt;
{% endhint %}

However, if you wish to show multiple groups different boards via your permission system, you should instead create gloss groups and set the group's default board to different boards.

#### [Learn how to make Gloss Groups](groups.md)

### Showing & Hiding Boards

You can hide the current board with

{% hint style="success" %}
/board hide
{% endhint %}

And show a specific board with

{% hint style="success" %}
/board show &lt;name&gt;
{% endhint %}

### Deleting Boards

You can delete boards with

{% hint style="success" %}
/board delete &lt;name&gt;
{% endhint %}

### Permission Locking Boards

You can assign a permission to any board so that even if the board is defaulted or supposed to be shown to everyone, only those with the permission you set will be able to view it.

{% hint style="success" %}
/board permit &lt;board&gt; &lt;permission&gt;
{% endhint %}

For permission names, give it a single node. For example using **/board permit &lt;board&gt; mortal** Would prevent anyone from using &lt;board&gt; without the permission **gloss.board.mortal.**

