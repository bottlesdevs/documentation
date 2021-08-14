---
description: The Flatpak package uses a different path for storing bottles.
---

# Migrate directories to Flatpak

## Migrate to Flatpak

In recent versions of the Flatpak and, the bottles are saved in a different location than the other packages, respecting the structure of the Flatpak package.

#### Paths differences

The other packages save the essential Bottles files, such as components, temps, and bottles, in the directory: `~/.local/share/bottles` . Flatpak saves these files in the Flatpak `data` directory: `~/.var/app/com.usebottles.bottles/data/bottles`.

#### Migrate old bottles to Flatpak

The migration is simple as it sounds - just move \(or copy\) the content of the path `~/.local/share/bottles` to the new one `~/.var/app/com.usebottles.bottles/data/bottles`

```bash
# make a copy
yes | cp -rf \
~/.local/share/bottles/* \
~/.var/app/com.usebottles.bottles/data/bottles

# or move (using rsync to take care of existing files)
rsync -a \
~/.local/share/bottles/* \
~/.var/app/com.usebottles.bottles/data/bottles
```

Restart Bottles and that's it.

