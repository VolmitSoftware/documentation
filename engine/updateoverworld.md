---
description: >-
  When the Overworld Dimension is updated, follow these steps to properly
  upgrade.
---

# Updating the Overworld

## How To Update Your Pack - Usual

Updating should only be done when needed to, or when you are ready to update the content from the latest release.   
**There is a simple command to update:**  
`/iris ^project overworld`  
This command does not update the current Overworld that is set in a `bukkit.yml` file, or any active iris world\(s\). Thus, you would need to remake or update the worlds to see any changes propagate.

## How To Update Your Pack - Loaded Worlds

{% hint style="danger" %}
**NOT RECOMMENDED** - Use at your own risk. Know what you are doing.  
This can and likely will cause issues in your world! You must back-up before doing this. We will not provide support if you did not.
{% endhint %}

Issues caused by this can be, but are not limited to:

* Broken chunks \(cut-offs\) between old and new chunks \(before & after the update\)
* Regenerated chunks that do not fit in with the old chunks
* Structures not spawning again when regenerating
* Caves not lining up
* Terrain layers not lining up

Know that updating your world does **NOT** update existing chunks unless you regenerate them

Now that you are aware of the risks:

**The command to force-update:**   
`/iris ^world myWorld overworld`   
This will update all biome and dimension data with the changes made to the pack.

