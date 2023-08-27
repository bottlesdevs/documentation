---
description: >-
  Runners are the heart of Bottles. They allow the execution of Windows software
  on Linux systems.
---

# Runners

## Types of runners

There are two types of runners in Bottles:

* Wine-based
* Proton-based

### Wine-based
**Wine-based** runners are based on the [Wine](https://www.winehq.org/) compatibility layer. They are used by default when creating all environments, and are also used for external prefixes imported into Bottles. We support a variety of Wine-based runners:

* Soda: One of our official runners. Based on Wine-TKG and Valve's Wine. Includes wine-staging and Proton patches. (Used by default in the Gaming and Application presets)
* Caffe: One of our official runners. Based on Wine-TKG. Includes wine-staging and Proton patches.
* Vaniglia: Our official 'vanilla' runner. Based on Wine upstream with wine-staging patches and a modern theme created by Joshua Ashton.
* [Wine-GE](https://github.com/GloriousEggroll/wine-ge-custom): Wine builds maintained by GloriousEggroll and used as a base for Proton-GE. Intended for use with non-Steam games.
* [Kron4ek](https://github.com/Kron4ek/Wine-Builds): Wine builds maintained by Kron4ek. Based on Wine upstream. Optionally includes wine-staging, TKG, and Proton patches as distinct builds.
* Lutris: Wine builds intended for Lutris. Comes in 3 varieties: Lutris, Lutris-GE (with patches from Wine-GE), and Lutris-GE-LoL (Wine-GE patches + League of Legends and other games using Riot Games Launcher).

Our official Wine builds can be found at https://github.com/bottlesdevs/wine.

### Proton-based
**Proton-based** runners are based on [Proton](https://github.com/ValveSoftware/Proton), a fork of Wine maintained by Valve Software primairly for Steam. Proton includes a variety of patches that improve game compatibility but may also disrupt compatibility with other software. We currently only support Proton-GE as an included Proton-based runner.

* [Proton-GE](https://github.com/GloriousEggroll/proton-ge-custom): A custom build of Proton maintained by GloriousEggroll. Contains several patches for specific games, implements [OpenVR](https://partner.steamgames.com/doc/features/steamvr/openvr) support and integrates DXVK (which can also be installed seperately from the bottle preferences page).

The Proton runner can be installed from the Bottles Preferences page and chosen on a bottle creation by selecting the Custom Environment. You can also switch from Wine to Proton at any time by changing your bottle preferences.

{% hint style="warning" %}
We personally recommend using the Proton runner only in special cases where there is a patch for a specific video game. **Valve collaborates in the development of Wine**, and many of the features integrated into Proton are also available in the latest versions of Wine.
{% endhint %}

## Installing and updating Runners

You can install new runners by clicking the download button next the runner of your interest.

![Bottles - Preferences - Runners](../.gitbook/assets/components/runners/Main.png)

If you're feeling fearless, you can enable Release Candidates ("Pre-release" option) to download and then test premature versions of runners, which may include greater software compatibility at the cost of bugs and possible regressions.

![Bottles - Preferences - Runners (Pre-release)](<../.gitbook/assets/components/runners/PreRelease.png>)

### Adding unlisted Runners

Runners are chosen for inclusion via a community-driven Bottles [repository](https://github.com/bottlesdevs/components).

If the runner you are looking for is not present, you can add it yourself by opening a Pull Request in the repository, [providing the runner manifest](https://github.com/bottlesdevs/components/blob/main/README.md#how-to-contribute).
