---
description: Bottles is available as a Flatpak!
---

# Installation

The Flatpak package works on most Linux distributions [supported by Flatpak](https://flatpak.org/setup/). It is fully sandboxed and comes with the necessary tools and dependencies.

{% hint style="info" %}
This is the most supported and tested way of installing Bottles.
{% endhint %}

{% tabs %}
{% tab title="Flathub" %}
Just press the button below:

[![Download on Flathub](https://flathub.org/assets/badges/flathub-badge-en.png)](https://flathub.org/apps/details/com.usebottles.bottles)
{% endtab %}

{% tab title="Beta" %}
Bottles Flatpak also provide a [Beta](https://github.com/flathub/com.usebottles.bottles/tree/beta) channel for testing purpose, maintained by our community.\
\
1\. Add the Flathub beta remote:

```bash
flatpak remote-add --user flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak update --appstream
```

2\. Then install Bottles:

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
wget -O bottles-source.zip https://github.com/bottlesdevs/Bottles/archive/main.zip
unzip bottles-source.zip
cd Bottles-main 
```

Build can be performed using `flatpak-builder` (installable using your distribution package manager like apt, dnf, ..):

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

