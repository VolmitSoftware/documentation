---
description: This page teaches you how to create a new project and set up Iris Studio
---

# Creating a new project

{% hint style="info" %}
This tutorial assumes you have Visual Studio Code installed and working.
{% endhint %}

## Video Tutorial

> To be added later

## Projects

For starters, projects are located in the `packs` folder \(found at `*/plugins/Iris/packs`\). Each project contains dimensions, biomes, regions and more. Each project has its own VSCode Workspace.

## Creating a new Project

Iris Studio is the system that allows you to easily design your own dimensions, or edit existing ones. To start using studio, first you will need to [turn on studio in the settings](../plugin/configuration.md#studio) and restart your server.

To start working with Iris Studio in a new project, we first have to create a new project. Do so with the in-game [studio create command](../plugin/commands.md#iris-studio-create-new). In this command you specify a template, which is the baseline from where we start editing.

{% hint style="info" %}
If you're following this Wiki as a tutorial to go over all [Understanding](understanding/) topics, you must use `/iris studio create <packName> template=example` as we will assume you use this later.

You can use this command for any project to create a copy, but if you're just looking to edit something small, you can also use `/iris studio open <packName>` to directly edit the original.
{% endhint %}

Once you run the command for your project, Iris will create a new project test world \(called a Studio World\) and should open VSCode with your project in it. After the first time, you can use the [studio open command](../plugin/commands.md#iris-studio-open-o) instead of the create command to re-open this project world & VSCode workspace. Once finished working on the Dimension, use the [studio close command](../plugin/commands.md#iris-studio-close-x) to delete the world and save your workspace progress.

{% hint style="info" %}
If Visual Studio Code does not open like it is supposed to, please navigate to the following folder: `*/plugins/Iris/packs/<packName>` and open `packName.code-workspace`.
{% endhint %}

{% hint style="info" %}
It is recommended that you use GitHub. If you are not familiar with using this program, check out the [documentation on GitHub](https://docs.github.com/en). Putting your project in a repository would give you the power to revert, to back-up and have many additional options regarding project changes.
{% endhint %}

