# Installation

## Using the AppImage

{% hint style="info" %}
This is the most tested and updated version ever.
{% endhint %}

First you need to download the latest release from our [website](https://usebottles.com/download) then, set executable permission to the `.AppImage` file:

```text
chmod +x Bottles-*-x86_64.AppImage
```

Move the file to a safe path where there is no risk of deleting them and double click on it, or launch via the terminal by typing:

```bash
./Bottles-*-x86_64.AppImage
```

#### ..or using [zap](https://github.com/srevinsaju/zap)⚡!

```bash
zap install bottles
```

### Snap

#### Snapcraft

 [![](https://snapcraft.io/static/images/badges/en/snap-store-black.svg)](https://snapcraft.io/bottles)

#### Manual build snap

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

### AUR

Bottles is available on AUR with 2 different packages:

* `bottles` provide the latest stable build
* `bottles-git` the latest commit from the GitHub repository

You can install using your preferred AUR helper:

```bash
yay -S bottles
paru -S bottles
```

or manually:

```bash
git clone https://aur.archlinux.org/packages/bottles
cd bottles-git
makepkg -si
```

### Flatpak

#### Flathub

{% hint style="info" %}
This package receives a total of **2 monthly updates**, scheduled on the **14th** and **28th** of each month \(but may vary in case of mainline release delays\).
{% endhint %}

[![Download on Flathub](https://flathub.org/assets/badges/flathub-badge-en.png)](https://flathub.org/apps/details/com.usebottles.bottles)

#### Beta

Bottles Flatpak also provide a [Beta](https://github.com/flathub/com.usebottles.bottles/tree/beta) channel for testing purpose.

#### Manual build flatpak

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

### Unofficial packages

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

