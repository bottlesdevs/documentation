# Why Bottles?

### Why a new application?

Bottles was born in 2017 as a personal need. I needed a practical way to manage my wineprefixes. I hate the idea of using applications that install me a version of wine for each application and I decided to create this application, based on the concept of using one or more wine prefixes as a "container" for all my applications.

In 2020 thanks to Valve, we have access to Proton. An optimized version of Wine for gaming. Thanks also to other projects like DXVK/VKD3D/Esync/Fsync/Shader compiler and others, we can run a large set of video games designed for Windows, on Linux.

The idea of creating an environment-based wineprefix manager comes from the standardization of dependencies and parameters necessary to run a game. On the other hand, we have software (often not up to date) that require environments and configurations different from those used in gaming. Hence the idea of managing separate environments.

### Why not just POL or Lutris?

Because they are similar but different applications. I want to create environments that contain more applications and games and where the wine version can be updated.

I also want to be able to export my bottles allowing easy sharing, with or without applications. In POL/Lutris we have the concept of "with this version of wine and these changes it works". In Bottles the concept is "this is my wine bottle, I want to install this software".

The goal with this version is also to integrate with the system in the best possible way. Being able to decide in a few bottles to run an .exe/.msi file and have control over it without having to open Bottles for each operation.

Bottles is close to what wineprefix means, since v.2 it provides a simplified method to generate environment-based bottles and thanks to other tools it simplifies the management but nothing more.

### Main features

There are some features that make Bottles unique:

* a powerful, integrated and written from scratch [dependency manager](../bottles/dependencies.md) based on a [community driven](broken-reference) and easy to expand repository
* version control to easily [restore a bottle state](../bottles/versioning.md) (goodbye disasters)
* management based on pre-configured [environments](../getting-started/environments.md) ready for **Gaming** or **Software**, with the most common dependencies pre-installed and an ad hoc configuration to immediately run a lot of software, you can also configure your environment from scratch
* [full-sandbox](broken-reference) (via Flatpak)
* easy config or full [backup](../bottles/backups.md) export and import, also cloning
* [automatically detect installed programs](../bottles/programs.md), no need to manually add to the programs list
* 360° [customization](../bottles/preferences.md) of the whole environment without having to go through winecfg
* a fully integrated [installers manager](../bottles/installers.md) also based on a [community driven](../bottles/installers.md#repository-and-contributions) repository

and much, much more. [Try Bottles](../getting-started/installation.md) to discover all the features we have designed to make it easier for you to run Windows software on Linux!

