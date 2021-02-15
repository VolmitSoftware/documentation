---
description: >-
  This will cover everything essential to know when starting a project. If you
  read everything from start to finish, you will know how to build a dimension
  and make the most important edits.
---

# Understanding

{% hint style="info" %}
We understand that this may be the first time you are doing something like this. This is why we chose to make the Understanding section elaborate and simple to understand.

We would like to warn new users that the Mastering section is more abstract and will contain less examples, images, videos etc. and will thus be more challenging to comprehend. That does however contain more settings and configuration than this section.
{% endhint %}

{% hint style="info" %}
Note before we begin. 

This page assumes you have [created a new project](../new-project.md) using `template=example` when creating the project, and that you also have VSCode open, and that you know how to close and \(re-\)open studio worlds and project files.

All references to folders are as you see them in the VSCode workspace \(`*/plugins/iris/packs/example/`\).  
Folders and files and are generally marked like `this`.  
If the referenced folder does not exist, you can create it. 

Make sure to make no mistakes when entering the name of the folder, as this will lead to issues later on.
{% endhint %}

Projects can be very complex or very simple. It's really how far you want to go. Below is a description of top level JSON object syntax and, further down, Iris types. This should be enough to get you set-up for basic editing.

Good luck and have fun :\)

## Basic JSON syntax

{% hint style="info" %}
From here on we assume you know this. Make sure to read this and not skip to editing. Thank me later.
{% endhint %}

### Creating Objects

You can easily create new objects by right clicking the folder of your project in VSCode, and creating the folder type if it doesn't exist. Then right click that new folder and click new file. Name it `<name>.json`. 

{% hint style="info" %}
Typically file names should be all lower case with hyphens \(-\) for spaces.
{% endhint %}

Objects start like this:

```text
{
    
}
```

Arrays look like this:

```javascript
[

]
```

Variables look like this:

```javascript
"variable": value,
"truthVariable": true
```

You will see these being used throughout, on top, and inside of one-another throughout the configurations.

### Content Assist

Once you have created a new top level type, use CTRL+SPACE in VSCode to show options & documentation about each property in the workspace.

This feature is an absolute life-saver in many cases. Make yourself familiar with it, you will use it a lot.

## Types

* [Dimensions](./#dimensions)
* [Regions](./#regions)
* [Biomes](./#biomes)
* [Generators](./#generators)
* [Objects](./#objects)
* [Structures](./#structures)
* [Loot](./#loot)
* [Entities](./#entities)

### [Dimensions](dimensions.md)

Dimensions are `json` files and they are placed in the `dimensions` folder. Typically you only have one dimension file in your entire project. The dimension file is the first and highest level file Iris looks at when generating. It describes regions, and other base settings. See [Dimensions](dimensions.md).

### [Regions](regions.md)

Regions are `json` files and they are placed in the `regions` folder. Regions are comparable to biomes, but they contain groups of biomes, instead of a single one. For example, some regions in the Overworld pack are `hot`, `temperate`, or `cold`. In regions, you define the biomes for each region. See [Regions](regions.md).

### [Biomes](biomes.md)

Biomes are `json` files and they are placed in the `biomes` folder. Biomes are what you would expect. They define block types, layers, objects and a lot of other stuff in the world. This is also where you reference noise generators to get your terrain shape. See [Biomes](biomes.md).

### [Generators](generators.md)

Generators are `json` files and they are placed in the `generators` folder. Generators are Noise Generators. Noise generators take a coordinate x,z or x,y,z and convert it into a height value. You can explore different base noise styles by using the [studio noise command](../../plugin/commands.md#iris-studio-noise). Generators can take multiple noise styles with additional options and are used to decide the shape of your terrain. See [Generators](generators.md).

### [Objects](objects.md)

Objects are a special type of file, `iob` and they are placed in the `objects` folder. Objects are the block schematics of Iris, comparable to World Edit schematics. You can use the [object commands](../../plugin/commands.md#iris-object-o) to create them easily. With objects you can also create sub folders inside the `objects` folder such as `objects/trees/tree-1.iob`. See [Objects](objects.md).

### [Structures](jigsaw.md)

Structures are `json` files and they are placed in the `structures` folder. Structures reference multiple Objects to create a tiled village/mineshaft/stronghold-like generator. These can also be referenced to by `Procedural Structures` in the support Discord. You can design one easily by using the [structure commands](../../plugin/commands.md#iris-structure-str). See [Structures](jigsaw.md).

### [Loot](loot.md)

Loot are `json` files and they are placed in the `loot` folder. Loot tables can be referenced when defining loot in different dimensions, biomes, regions and even structures. They decide which items spawn in the chests they are assigned to. See [Loot](loot.md).

### [Entities](entities.md)

Entities are `json` files stored in the `entities` folder. Entities can be spawned and have customized options for each entity object, such as armor, effects, attributes and more. See [Entities](entities.md).



#### Support

We offer support on our [Discord](https://discord.com/invite/3xxPTpT). Ask questions you cannot answer using the Wiki there.  
We ask you to look on the Wiki for a solution for your issue before going there.  
Thank you for using Iris!

* The Volmit Software Team

