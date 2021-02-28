---
description: This page will go over Basics in Objects
---

# Objects

## Video tutorial

> To be added later

## General information

Objects are Iris' schematics. They are used to place objects in the world.

They cannot be directly modified, so this will be a short guide on how objects can be:

* Created,
* Edited, 
* Added to the world, and
* Imported from EWG

### Create a new object

You can create a new object by building one in game and then saving it.  
The object can be any size under 512 x 256 x 512.  
Note that sizes that large will be heavy on the server to place.

After building the object, you can select it using the wand \(get a wand using the [wand command](../../plugin/commands.md#iris-object-wand-w)\) and then save it using the [save command](../../plugin/commands.md#iris-object-save). You can modify your selection with the other commands in the [object command section](../../plugin/commands.md#iris-object-o).

We recommend checking out the video above to see what they do precisely.

### Editing an object

You cannot directly edit an object from a file, but you can edit it in-game. You can do so by using the [paste command](../../plugin/commands.md#iris-object-paste), editing the structure and then using the same set of steps as with [Create a new object](objects.md#create-a-new-object) above.

### Adding an object to the world

Check out [this section ](biomes.md#5-objects)under Biomes to find how to implement objects.

### Import and object from EWG

{% hint style="warning" %}
This may not work any more.
{% endhint %}

You can import objects from Epic World Generator by putting `.EWG` schematic files in the `*/plugins/Iris/convert` folder and using the [convert command](../../plugin/commands.md#iris-studio-convert).

