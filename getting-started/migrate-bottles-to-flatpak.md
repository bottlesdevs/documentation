---
description: The Flatpak package uses a different path for storing bottles.
---

# Migrate bottles to FLatpak

## Migrate bottles to Flatpak

In recent versions of the Flatpak and, the bottles are saved in a different location than the other packages, respecting the structure of the Flatpak package.

#### Paths differences

The other packages save the essential Bottles files, such as components, temps, and bottles, in the directory: `~/.local/share/bottles` . Flatpak saves these files in the Flatpak `data` directory: `~/.var/app/com.usebottles.bottles/data/bottles`.

#### Migrate old bottles to Flatpak

In Bottles version **2021.07.14**, we have introduced an automatic bottle migration process that appears on first launch. This process **will be removed from version 2021.07.28** and you will need to proceed manually from that point on.

**Manual migration**

Manual migration is as simple as it sounds - just move the content of the path `~/.local/share/bottles` to the new one `~/.var/app/com.usebottles.bottles/data/bottles`.

Restart Bottles and that's it.

