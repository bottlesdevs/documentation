---
description: Use this guide if you need to reach other directories in the Flatpak.
---
# Expose directories

The Bottles Flatpak is sand-boxed and confined in its directories. It make use of [portals](https://docs.flatpak.org/en/latest/portal-api-reference.html) to let you open and save files in other directories.

Despite this, there are some cases where you may want to explicitly expose directories to the Flatpak, e.g.:

* let the [Importer](https://docs.usebottles.com/bottles/import-from-other-managers) find windows prefixes from other managers directories
* use the file chooser provided by the runner to open/save files in your system, outside the sandbox

To achieve this, we need to use an external program named [Flatseal](https://flathub.org/apps/details/com.github.tchx84.Flatseal), it can be easily installed from Flathub using a compatible store like GNOME Software, elementary Appcenter or Discover. It is also possible to install trough the command line:

```bash
flatpak install com.github.tchx84.Flatseal
```

On first launch you need to select Bottles from the left menu, then scroll to the Filesystem section and make your choices.

![Flatseal > Bottles](<../.gitbook/assets/image (41).png>)

We suggest to not expose all your system or home but manually add each directory in **Other files**. In the following example we are exposing the `~/Games` folder from our home (the default location for Lutris windows prefixes).

![Exposing the \~/Games directory](<../.gitbook/assets/image (40).png>)

Then the Bottles Importer will see the new directory.

