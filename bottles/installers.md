---
description: Install new Windows programs in a few clicks in a guided and easy process.
---
# Installers

{% hint style="warning" %}
This is an experimental feature, use it with caution.
{% endhint %}

Installers are set of rules used by Bottles to install a program in a bottle, in a completely silent and automated way.

These installers take care of configuring the bottle, installing the necessary dependencies, installing the software and making it available to the user with settings that ensure that everything works in the best way.

The novelty introduced by our own installers is the use of the integrated dependency system. This in fact does not use external scripts to install and configure dependencies but uses the same dependency manager accessible from Bottles, so each one of these is automatically managed by Bottles, in the same way you would do it manually from the dependencies page.

Each installer configures the executable in your system (at the moment it does not happen if you are using Flatpak), allowing you to access it at any time from the applications menu of your Desktop Environment. These are done through the Bottles CLI, making sure they use your bottle’s configuration and environment.

At launch, only 3 installers are available (Epic Games Store, Steam, Uplay). This is indeed an experimental feature, we will add new installers in the future. [Here](https://usebottles.com/appstore/) you can see the full catalog.

### Use installers

To test this feature, you must first enable it from the experiments in the Bottles preferences.

![Preferences > Experiments > Installers](<../.gitbook/assets/image (36).png>)

Once enabled, a new Installers item will pop up in the sidebar of your bottle page, click it and you will see the list of supported installers. To install one, just press Install and wait for the process to finish.

![Bottle > Installers](<../.gitbook/assets/image (37).png>)

Once the installation is completed, you will see the new program in the applications menu of your Desktop Environment or in the programs list of your bottle. 

As we said, this is an **experimental feature**, it is under early development and should be used only for testing purposes until we hit the first stable release.

### Repository and contributions

All installers are placed in a [public repository](https://github.com/bottlesdevs/programs) where any user can contribute. There are few [guidelines](https://github.com/bottlesdevs/programs/blob/main/GUIDELINES.md) that users can follow to make his own installers.
