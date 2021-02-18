---
description: Introduction into Dimensions
---

# Introduction to the Engine

{% hint style="info" %}
If you would like to change something simple and quick, skip to [Creating a Project](new-project.md#creating-a-new-project), make sure to read [Understanding](understanding/) \(both are quite short\), and then navigate to your [type](understanding/#types).
{% endhint %}

## Iris is a dimension engine

This plugin is not just a block-placer. Iris comes with additional features to make the experience feel special. Examples of these features are custom particles and mob spawns.

Iris comes with several tools designed to allow the manipulation and handling of world generation with ease and power. Additionally, Iris makes full use of the VSCode workspace system, allowing for handy tool-tips and autocomplete in VSCode.

A core philosophy of Iris is flexibility, meaning that Iris is capable of generating any terrain imaginable \(within the technical limitations of Minecraft, sadly\), while also catering towards those who just want pretty looking terrain without much fuss.

## **How Iris handles your worlds**

For any given world, Iris takes a set of instructions and uses that to shape the world. You are in full control; whether that is determining which block should be placed at any given location, how biomes should be arranged, how structures should spawn, and so on, you decide everything!

Such a set of instructions is called a pack. The Overworld is an example of a pack. Iris world generation is handled on a per-world basis, meaning you can set up any multitude of worlds, each with their own custom pack, or have multiple worlds share the same pack if you so desire.

If a world hasn’t been set up with Iris then don’t worry - only worlds which are set up with Iris will be affected by Iris. We're not destroying your existing worlds.

## **Specifics of a pack**

An Iris pack is a collection of configuration files that define how Iris generates a world. Packs are designed to be highly customizable - allowing you to create and manipulate world generation to your liking - and packs are made easy to understand and have logical structures - allowing for easy yet powerful editing. If the Iris engine was a builder, then packs would be the blueprints that tell Iris what to do.

Packs are stored within the `*/plugins/iris/packs` folder within your server’s files, and can be broken down into several folders, each containing a separate group of configuration files. This includes things like biomes, schematics, terrain generators and more. \(We will cover the specifics later on!\).

## Using templates

If creating a pack is not your thing, Iris has you covered - The Iris team has created the Overworld pack. This, as a de-facto standard, comes bundled with Iris, and contains a set of stunning pre-made biomes, thousands of schematics, and utilises almost all of Iris’ comprehensive features. The Overworld pack, as well as other community curated packs, can be found on the [Iris Dimension Collection](https://github.com/IrisDimensions), hosted on GitHub. You can use the [Download Command](../plugin/commands.md#iris-download-dl) to download the pack directly. You can then use the `template` parameter when creating a workspace / project you can edit: e.g. `/iris std create myPack template=overworld`.

