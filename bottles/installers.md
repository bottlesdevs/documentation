---
description: Install new Windows programs in a few clicks in a guided and easy process.
---

# Installers

Installers are a set of rules used by Bottles to install a program in a bottle, in a completely silent and automated way.

{% hint style="info" %}
Installers was introduced with Bottles 2022.2.14, read [here](https://usebottles.com/blog/release-2022.2.14/) the release post.
{% endhint %}

These installers take care of configuring the bottle, installing the necessary dependencies, installing the software and making it available to the user with settings that ensure that everything works in the best way.

The novelty introduced by our own installers is the use of the integrated dependency system. This in fact does not use external scripts to install and configure dependencies but uses the same dependency manager accessible from Bottles, so each one of these is automatically managed by Bottles, in the same way you would do it manually from the dependencies page.

Each installer configures the executable in your system (at the moment it does not happen if you are using Flatpak), allowing you to access it at any time from the applications menu of your Desktop Environment. These are done through the Bottles CLI, making sure they use your bottle’s configuration and environment.

At launch 7 installers are available (Epic Games Store, Steam, Uplay, Origin, EA Games, GOG, Battle.net).

### Use installers

Below is a video showing how to use the Installers in Bottles.

{% embed url="https://www.youtube.com/watch?v=0BQjFlEdSVA" %}

To use the installers you obviously need a bottle, so select the one you are interested in or create a new one. In the sidebar access the Installers section.

![Bottles - Installers](<../.gitbook/assets/installers (1).png>)

Choose the installer you want and press the download icon. It will automatically configure your bottle and install the program. When the installation finish, you will see a new entry in your bottle's programs list.

Each installer came with its maintainer review, you can access it from the context menu or from its dedicated page on the [apps catalog](https://usebottles.com/appstore/).

{% hint style="info" %}
Currently it is not possible to launch an installer from our website, we are working to provide this feature.
{% endhint %}

All installers are placed in a [public repository](https://github.com/bottlesdevs/programs) where any user can contribute. If you are interested in make your own installers, please read the [maintainers documentation](https://maintainers.usebottles.com).

### Note for architecture

**Important note** installers can declare their architecture so if the bottle created is `Win64` it won't see `Win32` installers and vice versa.

### Refresh installation

Installers can be installed multiple times, also in the same bottle. If you break anything or just want to use the latest installer (as these can receive updates from maintainers), just install it again. Currently Bottles doesn't notify installers updates but will be able to do so in the near future.
