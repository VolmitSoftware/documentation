# Cull Entities

## Cull Entities

The cull entities action **strives to remove some entities**, not all of them. It simply shaves off the excess entities without affecting players, and dealing with high entity counts at the same time. There are a boatload of benefits with this action, especially when it is automatic.

* You can fine tune what entities are allowed to be culled based on many properties such as if they have a name, are tamed, are in caves or not and so much more
* Killing only some entities saves your server from dropping into a full gc sometimes which is why removing all entities is so bad. **Removing all entities will just make bukkit spawn more anyways.**
* Cull entities is called automatically when there are dense clusters of entities, but only in the areas which are causing problems.

{% hint style="info" %}
This action is highly dependent on how you have configured the culling rules in the react config.yml
{% endhint %}

### Usage

```text
/re act cull-entities
```

### Selector Usage

{% tabs %}
{% tab title="Position" %}
You can specify [where ](./#positional-selectors)you wish to cull entities.

```text
/re act cull-entities @c:look+3
```

{% hint style="success" %}
The default position selection is **@c:\*** or every loaded chunk in every world.
{% endhint %}
{% endtab %}

{% tab title="Entity" %}
You can specify which entities you want to attempt to cull. Remember, this action depends on your cull rules. If you only select pigs in a chunk, it will only try to cull pigs, even if it could cull other entities in that chunk. Even if you select an entity type, **it still has to follow your culling rules.**

```text
/re act cull-entities @e:pig&sheep
```

{% hint style="success" %}
The default entity selection is **@e:\*&!player** meaning everything but players.
{% endhint %}
{% endtab %}
{% endtabs %}

#### Combining Selectors

```text
/re act cull-entities @c:look+3 @e:cow&chicken
```

> Culls cows and chickens at the chunk you are looking at plus a radius of three chunks out.

### Aliases

| Node |
| :--- |
| cull-entities |
| ce |

