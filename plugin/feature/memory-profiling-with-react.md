---
description: Profile plugin memory usage estimates.
---

# Memory Profiling

## Profiling Plugin Memory

Due to the way java is, memory profiling can be quite tricky. Especially because of how inaccurate it can be due to GC. However, react has the ability to utilize classmexer which takes advantage of java instrumentation and java agents. This guide will assist you in setting up react to utilize the class mexer.

{% hint style="danger" %}
Please keep in mind that these are heavy estimates. If one plugin reports high memory, continue to check it every so often. There is no perfect way to determine the exact amount of memory a plugin is using.
{% endhint %}

### System Requirements

* The server must have internet access for setup only
* Edit access to the start script / command for your server \(i.e. java -Xmx -Xms -jar\)
* React 6.548+

### Install the Agent

To install the classmexer agent, simply run the following command either ingame or in your console

```text
/react installagent
```

You should see the following output

```text
> react installagent
[React]: Downloading Volume Memory Agent.
[React]: Downloading: 11%
[React]: Downloading: 22%
[React]: Downloading: 34%
[React]: Downloading: 45%
[React]: Downloading: 56%
[React]: Downloading: 67%
[React]: Downloading: 78%
[React]: Downloading: 89%
[React]: Downloading: 100%
[React]: Download Complete!
```

Once the agent has been downloaded, you will notice a jar file named "classmexer.jar" in the root directory of your server \(whereever your server jar is\)

### Configure your Launch Arguments

Since we are utilizing a javaagent, you must specify it during startup. This is very simple. For example, if you have the following launch command

```text
java -Xmx2g -Xms1m -XX:+UseG1GC -jar spigot-1.12.2.jar
```

You will need to specify the javaagent just before -jar xxx

```text
java -Xmx2g -Xms1m -XX:+UseG1GC -javaagent:classmexer.jar -jar spigot.jar
```

### Profiling Plugin Usage

Now that you have setup the classmexer, you can now use react to see ESTIMATES on memory.

You can specify on a per plugin basis like so

```text
> react memory Essentials
[React]: Essentials is using ~27.96 MB of memory.
```

You can also get the top use from all plugins like so

```text
> react memory top
[React]: Computing Memory usage for 13 plugins
[React]: Computing Sizes: 8%
[React]: Computing Sizes: 38%
[React]: Computing Sizes: 69%
[React]: Computing Sizes: 100%
FastAsyncWorldEdit: 86.93 MB
DirePluigin: 85.24 MB
VolumedPlugin: 84.62 MB
PlaceholderAPI: 84.55 MB
Vault: 79.17 MB
BileTools: 79.10 MB
Fulcrum: 70.32 MB
Multiverse-Core: 70.00 MB
ProtocolLib: 69.99 MB
Essentials: 64.75 MB
WorldEdit: 64.65 MB
React: 59.30 MB
Wormholes: 57.36 MB
```

{% hint style="warning" %}
Using /re mem top \(/react memory top\) can sometimes freeze if something unexpected happens when profiling. Use /re mem &lt;plugin&gt; instead.
{% endhint %}

