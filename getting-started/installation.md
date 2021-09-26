---
description: 'We offer Bottles in different packages, make your choice!'
---

# Installation

Bottles is officially provided as AppImage, Flatpak, Snap, AUR, deb package. There are also other packages maintained by our community, like Fedora and AUR \(bottles-git\).

### AppImage

This is the most tested and updated version ever. It is a portable package that should works on every distribution.

{% tabs %}
{% tab title="zap⚡" %}
First [install zap](https://github.com/srevinsaju/zap#getting-started-), then:

```bash
zap install bottles
```
{% endtab %}

{% tab title="Traditional way" %}
First you need to download the latest release from our [website](https://usebottles.com/download) then, set executable permission to the `.AppImage` file:

```text
chmod +x Bottles-*-x86_64.AppImage
```

Move the file to a safe path where there is no risk of deleting them and double click on it, or launch via the terminal by typing:

```bash
./Bottles-*-x86_64.AppImage
```
{% endtab %}
{% endtabs %}

### Snap

{% tabs %}
{% tab title="Snapcraft" %}
Just press the following button to install it from the Snapcraft store.

 [![](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/bottles)
{% endtab %}

{% tab title="Manual build" %}
Download the latest bottles source from GitHub:

```bash
wgen -O bottles-source.zip https://github.com/bottlesdevs/Bottles/archive/master.zip
unzip bottles-source.zip
cd bottles-source
```

Install snapcraft, e.g. on Ubuntu 20.04+:

```bash
apt install snapcraft
```

then build, install \(using the `--dangerous` option to skip the checksum\) and run:

```bash
snapcraft
snap install bottles*.snap --dangerous
snap run bottles
```
{% endtab %}
{% endtabs %}

#### AUR

Bottles is available on AUR with 2 different packages:

* `bottles` provide the latest stable build
* `bottles-git` the latest commit from the GitHub repository

{% tabs %}
{% tab title="AUR helper" %}
Bottles can be installed using an AUR helper like `yay` or `paru`:

```bash
yay -S bottles # or bottles-git
paru -S bottles # or bottles-git
```
{% endtab %}

{% tab title="Traditional way" %}
```bash
git clone https://aur.archlinux.org/packages/bottles # or bottles-git
cd bottles # or bottles-git
makepkg -si
```
{% endtab %}
{% endtabs %}

### Flatpak

This is the only full-sandboxed version. It bundle all the needed dependencies and tools and works an all distributions [supported by Flatpak](https://flatpak.org/setup/).

{% tabs %}
{% tab title="Flathub" %}
Just press the button below:

[![Download on Flathub](https://flathub.org/assets/badges/flathub-badge-en.png)](https://flathub.org/apps/details/com.usebottles.bottles)
{% endtab %}

{% tab title="Beta" %}
Bottles Flatpak also provide a [Beta](https://github.com/flathub/com.usebottles.bottles/tree/beta) channel for testing purpose, maintained by our community.  
  
1. Add the Flathub beta remote:

```bash
flatpak remote-add --user flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak update --appstream
```

2. Then install Bottles:

```bash
flatpak install --user flathub-beta com.usebottles.bottles
```
{% endtab %}

{% tab title="Manual build" %}
We need the following dependencies:

* org.gnome.Sdk
* org.gnome.Sdk.Compat.i386
* org.freedesktop.Sdk.Extension.toolchain-i386

Download the latest bottles source from GitHub:

```bash
wgen -O bottles-source.zip https://github.com/bottlesdevs/Bottles/archive/master.zip
unzip bottles-source.zip
cd bottles-source
```

Build can be performed using `flatpak-builder` \(installable using your distribution package manager like apt, dnf, ..\):

```bash
flatpak-builder --repo=bottles --force-clean --user build-dir com.usebottles.bottles.yml
flatpak remote-add --user bottles bottles --no-gpg-verify
flatpak install --user bottles com.usebottles.bottles
```

Then run using `flatpak` command:

```bash
flatpak run com.usebottles.bottles
```
{% endtab %}
{% endtabs %}

### Other packages

Our community provides non-official packages for installing Bottles on some distributions.

#### Fedora

Bottles is available on Fedora [repositories](https://src.fedoraproject.org/rpms/bottles) thanks to [@atim](https://src.fedoraproject.org/user/atim) so you can install using `dnf`:

```bash
$ dnf install bottles
```

### Build from source

You can also build Bottles from source.

Requirements:

* meson
* ninja
* python3
* glib
  * `glib2-devel` on Fedora
  * `libglib2.0-dev` on Debian/Ubuntu

Clone Bottles from GitHub:

```bash
git clone https://github.com/bottlesdevs/Bottles.git
cd Bottles
```

and build using `meson` and install using `ninja`:

```bash
mkdir build
meson build && cd build
ninja -j$(nproc)
$ ninja install
```

