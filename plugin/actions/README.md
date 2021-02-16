---
description: >-
  The action system is a collection of actions which are used automatically and
  via manual invocation
---

# Actions

## Actions

A list of all current actions in react.

| Action | Description | Selectors |
| :--- | :--- | :--- |
| [Fix Lighting](fix-lighting.md) | Fixes lighting in the area | [Position](./#positional-selectors) |
| [CPU Score](cpu-score.md) | Benchmarks the CPU |  |
| [Dump](dump.md) | Dumps data to a pastebin. |  |
| [File Size](untitled.md) | Reads server file sizes for totals |  |
| [Timings](timings.md) | Fires a timings report and finishes it for you. | [Time](./#time-selectors) |
| [Chunk Test](chunk-test.md) | Benchmarks chunk performance in the area | [Position](./#positional-selectors), [Time](./#time-selectors) |
| [Cull Entities](cull-entities.md) | Culls entities \(removes some not all\) | [Position](./#positional-selectors), [Entity](./#entity-selectors) |
| [Collect Garbage](collect-garbage.md) | Invokes System.gc\(\). Warning, dangerous. |  |
| [Purge Entities](purge-entities.md) | Purges all "typical" entities | [Position](./#positional-selectors), [Entity](./#entity-selectors) |
| [Purge Chunks](purge-chunks.md) | Purges chunks which are outside of all player views | [Position](./#positional-selectors) |
| Lock / Unlock Fluid | Locks or unlocks fluid depending on action used | [Position](./#positional-selectors), [Time](./#time-selectors) |
| Lock / Unlock Redstone | Locks or unlocks redstone depending on action used | [Position](./#positional-selectors), [Time](./#time-selectors) |
| Lock / Unlock Hoppers | Locks or unlocks hoppers depending on action used | [Position ](./#positional-selectors)[Time](./#time-selectors) |

## Selectors

Action selectors allow you to control actions in a fine tuned way.

### Positional Selectors

Positional selectors allow you to control the position and area that an action will fire in. Positional selectors work on a chunk grid. This means you select a position based on an area of chunks. The default is every chunk in every world. You can tweak this like so.

{% tabs %}
{% tab title="This Chunk" %}
You can specify the chunk you are currently in as a reference point as **"this"**

```text
@c:this
```

You can use **"this"** as the center of a chunk radius selection also.

```text
@c:this+3
```

{% hint style="warning" %}
The "+NUM" suffix specifies the amount of CHUNKS to expand outwards from the reference point. It is advised you keep this below 10.
{% endhint %}
{% endtab %}

{% tab title="That Chunk" %}
You can specify the chunk you are looking at \(within your view distance\) instead of the chunk you are actually inside of with the **"look"** tag.

```text
@c:look
```

You can use **"look"** as the center of a chunk radius selection also.

```text
@c:look+4
```

{% hint style="warning" %}
The "+NUM" suffix specifies the amount of CHUNKS to expand outwards from the reference point. It is advised you keep this below 10.
{% endhint %}
{% endtab %}

{% tab title="Specific Chunks" %}
You can reference a specific chunk instead of **"this"** or **"look"** by specifying the world.x,z

```text
@c:world_nether.15,13
```

{% hint style="info" %}
Note that you cannot specify a radius such as ~~@c:ww.15,13+3~~ \_\_as this is not allowed
{% endhint %}

You can specify every **loaded** chunk in a given world also by using a star \(asterisk\)

```text
@c:world_the_end.*
```

Or specify every loaded chunk

```text
@c:*
```
{% endtab %}
{% endtabs %}

### Time Selectors

Time selectors allow you to control how long an action should run for

| Measurement | Example | Suffix |
| :--- | :--- | :--- |
| Game Ticks | `@t:8t` | t |
| Milliseconds | `@t:150ms` | ms |
| Seconds | `@t:5s` | s |
| Minutes | `@t:2m` | m |
| Hours | `@t:3h` | h |

### Entity Selectors

Entity selectors allow you to control which entity types to act upon \(or which not to\). Simply specify an [Entity Type](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html)

### Selection Syntax

There are a couple extra tricks that are good to know when using selectors

{% tabs %}
{% tab title="AND" %}
And literally means AND. It means combine these, or to compound. It uses the **"&"** symbol.

```text
@c:this&look
```

> Adds the chunk you are currently in, AND the chunk you are looking at into the selection
{% endtab %}

{% tab title="NOT" %}
Not literally means not and is represented by the **"!"** symbol

```text
@c:this+3&!look
```

> Specifies a radius of 3 chunks around your location, but SUBTRACTS the chunk you are looking at out of the selection. The "&!" means A AND NOT B \(or but not\)
{% endtab %}
{% endtabs %}

