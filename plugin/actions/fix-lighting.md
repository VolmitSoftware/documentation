# Fix Lighting

## Fix Lighting

{% hint style="info" %}
This action requires [FastAsyncWorldEdit ](https://github.com/IntellectualSites/FastAsyncWorldEdit)to be executed.
{% endhint %}

Fix lighting is a simple action which fixes lighting in the specified chunks. This action is useful for many reasons.

* Fixing lighting
* Fixing ghost chunks
* Fixing entity or tile entity client-desync
* Fixing incorrect biome caches on the client

### Usage

```text
/re act fix-lighting
```

### Selector Usage

{% tabs %}
{% tab title="Position" %}
Positional selectors are used to specify chunks to relight

```text
/re act fix-lighting @c:this+3
```

{% hint style="success" %}
The default position selection is **@c:\*** or every loaded chunk in every world.
{% endhint %}
{% endtab %}
{% endtabs %}

### Aliases

| Node |
| :--- |
| fix-lighting |
| fl |

