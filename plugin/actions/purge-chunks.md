# Purge Chunks

## Purge Chunks

Purging chunks is pretty straight-forward. React will safely unload \(and save\) chunks that are outside of all player view distances.

### Usage

```text
/re act purge-chunks
```

### Selector Usage

{% tabs %}
{% tab title="Position" %}
You can specify [what ](./#positional-selectors)chunks you wish to purge, though **react will not purge chunks inside any players view distance** even if you explicitly tell it to.

```text
/re act purge-chunks @c:world_nether.*
```

{% hint style="success" %}
The default position selector is **@c:\*** or all loaded chunks in all worlds
{% endhint %}
{% endtab %}
{% endtabs %}

### Aliases

| Node |
| :--- |
| purge-chunks |
| pc |



