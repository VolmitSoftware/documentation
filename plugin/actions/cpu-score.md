# CPU Score

## CPU Score

{% hint style="warning" %}
The CPU Score action pushes the server's processor on a separate thread from the game. If you are utilizing most of your processor cores, this action will significantly affect server performance, and result in a lower score.

**Run this action for a smaller increment of time first** to ensure it wont affect server performance while benchmarking for longer periods of time.
{% endhint %}

The cpu score action benchmarks your processor and results in three values after the benchmark has completed.

`MIN <- SPREAD -> MAX`

* The min value represents the lowest score your processor has gotten
* The max value represents the highest score your processor has gotten
* The spread is simply the difference between the min and max. A lower spread means your processor is capable of dealing with higher loads at unexpected times very well.

{% hint style="info" %}
Your score min and max are stored in memory, meaning multiple benchmarks will compound on your existing score, allowing you to see the highest score ever since startup.
{% endhint %}

### Usage

```text
/re act cpu-score
```

### Selector Usage

{% tabs %}
{% tab title="Time" %}
You can specify how long you wish to benchmark

```text
/re act cpu-score @t:10s
```

{% hint style="success" %}
The default time selector is **@t:5s** or 5 seconds.
{% endhint %}
{% endtab %}
{% endtabs %}

### Aliases

| Node |  |
| :--- | :--- |
| cpu-score |  |
| cs |  |
| cpu |  |
| cscore |  |
| benchmarkcpu |  |

