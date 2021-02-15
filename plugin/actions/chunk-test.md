# Chunk Test

## Chunk Test

The chunk test command pulls information about all of the selected chunks and gives a report of usage in the chunks

{% hint style="info" %}
There is a bit of assuming involved in this as there is no perfect way to check how much each chunk is truly using, however this is usually good enough for getting the "gist" of an area
{% endhint %}

### Usage

```text
/re act chunk-test
```

### Selector Usage

{% tabs %}
{% tab title="Position" %}
You can specify what chunks to test with the [position selector](./#positional-selectors)

```text
/re act chunk-test @c:this+3
```

{% hint style="success" %}
The default position selection is **@c:\*** or every loaded chunk in all worlds
{% endhint %}
{% endtab %}

{% tab title="Time" %}
You can specify a [time frame](./#time-selectors) to benchmark the selected chunks

```text
/re act chunk-test @t:20s
```

{% hint style="success" %}
The default time selection is **@t:1s** or 1 second
{% endhint %}
{% endtab %}
{% endtabs %}

#### Combining selectors

```text
/re act chunk-test @t:30s @c:this+3
```

> Benchmarks the chunks around YOU in a radius of 3 chunks for 30 seconds

### Aliases

| Node |
| :--- |
| chunk-test |
| ctest |
| ct |

