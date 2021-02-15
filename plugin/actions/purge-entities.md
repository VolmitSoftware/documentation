# Purge Entities

## Purge Entities

Purging entities removes all entities in the specified chunk.

{% hint style="info" %}
Purge entities responds to the list of entities it is allowed to remove. **It will not remove entities that are not on it's allowed list.** You can use the force tag to "force" it to remove everything \(except for players\)
{% endhint %}

### Usage

```text
/re act purge-entities
```

### Selector Usage

{% tabs %}
{% tab title="Position" %}
You can specify [where ](./#positional-selectors)you want to remove entities.

```text
/re act purge-entities @c:this+2
```

{% hint style="success" %}
The default position selection is **@c:\*** or all loaded chunks in all worlds
{% endhint %}
{% endtab %}

{% tab title="Entity" %}
You can specify [what ](./#entity-selectors)you want to purge

```text
/re act purge-entitities @e:cow&pig&sheep
```

{% hint style="success" %}
The default entity selection is **@e:\*&!player** or everything but players
{% endhint %}

{% hint style="info" %}
When using force, this action will only force purge these types of entities
{% endhint %}
{% endtab %}
{% endtabs %}

#### Combining Selectors

```text
/re act purge-entities @c:world_nether.* @e:*&!ghast -f
```

> Forcefully \(-f\) removes everything except for ghasts in the nether.

### Using the Force

Using force will ignore the allowed-purge list in the config and kill entities anyways, ignoring players. Make sure you specify what types of entities you wish to kill or react will literally kill everything

```text
/re act purge-entities @c:this @e:cow -f
```

> This force kills all cows in your chunk

### Aliases

| Node |
| :--- |
| purge-entities |
| pe |

