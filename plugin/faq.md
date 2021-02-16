---
description: Use the sidebar or search to find what you need.
---

# FAQ

## Does React work with PandaWire?

Yes, react works quite well with pandawire. It might be a good idea to disable redstone goals in RAI if you are using pandawire. Pandawire is a hack on the redstone blocks themselves, it is superior to react's redstone capabilities, but if you pair them togeather its a nice combo.

In plugins/React/goals/suppress-redstone.json Ensure enabled is false

```javascript
{
    "reaction": {
        "near": "redstone",
        "time": "1s",
        "type": "lock_redstone"
    },
    "author": "React",
    "name": "Suppress Redstone",
    "description": "Reduces Redstone usage",
    "interval": "1s",
    "conditions": ["redstone_tick_usage>0.33"],
    "enabled": false
}
```

## Does React work with ClearLagg?

Yes! You can use ClearLagg and React side by side, however they will both be doing similar things and it may be wise to use React's goal system instead. For example you could create a custom goal to auto purge drops every interval or under any conditions.

For example this goal would purge all drops every minute, every single time,

```javascript
{
    "reaction": {
        "near": "entity",
        "type": "purge_entities",
        "entity": "DROPPED_ITEM"
    },
    "author": "cyberpwn",
    "name": "Drop Purger",
    "description": "Purges drops",
    "interval": "1m",
    "conditions": [],
    "enabled": true
}
```

However you could improve this goal by adding a condition to only purge drops if the drops exceed a certain count

```javascript
{
    "reaction": {
        "near": "entity",
        "type": "purge_entities",
        "entity": "DROPPED_ITEM"
    },
    "author": "cyberpwn",
    "name": "Drop Purger",
    "description": "Purges drops",
    "interval": "1m",
    "conditions": [
        "entitydrop>250"
    ],
    "enabled": true
}
```

This would only run every minute, checking if the amount of drops is greater than 250, if it is then the purger runs that minute.

## Does React work with MythicMobs?

React now has mythic mobs support as of version 6.555. First, take a look at the config.yml under mythic-mobs \(in react\)

```yaml
  mythic-mobs:

    # If mythic mobs is enabled, use mob stacking on them
    allow-stacking: false

    # If mythic mobs is enabled, allow purging of them with 
    # /re a pe
    allow-purging: true

    # If mythic mobs is enabled, allow culling of them with 
    # /re a ce
    allow-culling: true
```

From here you can globally control how react interacts with mythic mobs, if at all. You can also modify the culling rules too

```yaml
entity-types:
  culling-rules:
  - '@Refuse Tamed'
  - '@Defer Mythic' # You can defer mythic. (or @Prefer/@Refuse)
  - '@Defer Named'
  - '@Defer Leashed'
  - '@Defer Stacked'
  - '@Defer Ridden'
  - '@Defer Young'
  - '@Defer Non-Living'
  - '@Defer Grounded'
  - '@Defer Passive'
  - '@Defer Lit'
  - '@Prefer Living'
  - '@Prefer Hostile'
  - '@Prefer Mature'
  - '@Prefer Underwater'
  - '@Prefer Airborne'
  - '@Prefer Projectiles'
  - '@Prefer Caves'
  - '@Restrict Pig,Cow,Sheep,Chicken = 14'
  - '@Restrict Zombie,Spider,Skeleton,Creeper = 14'
  - '@Restrict Wolf,Ocelot,Horse = 9'
  - '@Restrict Dropped Item = 30'
  - '@Restrict Experience Orb = 28'
  - '@Restrict Area Effect Cloud = 28'
```

## What is a positional selector

A positional selector is used to control WHERE an action fires in react. You can invoke these wherever you see an @c in the action. Let's start with a very simple example. Say we want to kill all entities in only the chunk we are standing in

```text
/re act purge-entities @c:this
```

It is also possible to expand the radius of chunks the action affects. Say we want a radius of 2 chunks \(so 3x3 chunks with you in the center\)

```text
/re act purge-entities @c:this+2
```

Perhaps we only want to use purge-entities in world\_nether?

```text
/re act purge-entities @c:world_nether.*
```

We can also directly specify a chunk too

```text
/re act purge-entities @c:world_nether.34,5
```

### Multiple Selections

You can also select multiple things in the same selector with the & symbol.

```text
/re act purge-entities @c:this&world_nether.*
```

### Negative Selections

Negative selections allow you to create a selection, and subtract out something from that selection. Notice we use the ! symbol to mark it as subtract. We select a radius of 3 chunks around us and subtract out the inner circle of 2 radius, resulting in a 4x4 ring of chunks \(3 chunks away\) from the center.

```text
/re act purge-entities @c:this+3&!this+2
```

## Turn off all Redstone & Tile Optimizations

Turning off all optimizations for redstone and tiles entities is pretty simple.

### Disable Redstone Suppression

Redstone suppression prevents too much redstone from activating at once by pausing it in areas. You can disable this in **React/goals/suppress-redstone.json** Simply set enabled to false.

```javascript
{
    "reaction": {
        "near": "redstone",
        "time": "1s",
        "type": "lock_redstone"
    },
    "action-health-regen": 1,
    "author": "React",
    "action-health-max": 400,
    "name": "Suppress Redstone",
    "description": "Reduces Redstone usage",
    "interval": "1s",
    "conditions": ["redstone_tick_usage>0.33"],
    "enabled": false,
    "action-health-damage": 70
}
```

### Disable Tile & Entity Tick Smearing

Tile tick smearing prevents too many tiles from ticking all at once, it "smears" the tick list across multiple ticks. You can disable this in **React/config.yml** by setting enabled to false under tiles, under tick-smearing

```yaml
tick-smearing:
  tiles:

    # The maximum tile tick time before throttling
    max-time: 35.0

    # Enable entity tick throttling
    enable: true

    # Allow the tile tick throttle to be X higher than the 
    # current time to prevent
    # odd skipping of entities, and to allow room for error.
    seperation-bias: 0.07

    # How many ticks should the tick time be averaged across 
    # to compute biases
    smear-factor: 50.0
```

## Disable Fast Leaf Decay

To disable fast leaf decay, simply open up the config.yml in the react folder and set **enabled to false**.

```yaml
fast-leaf-decay:
    fast-destroy: true
    max-ms: 0.8
    trigger-on-decay: true
    instantaneous: false
    decay-period: 5

    # Set this to false
    enabled: false
```

