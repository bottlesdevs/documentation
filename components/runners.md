---
description: >-
  Runners are the heart of Bottles. They allow the execution of Windows software
  and the creation of wineprefixes.
---

# Runners

## Types of runners

There are two types of runners in Bottles:

* Wine
* Proton

The **Wine** runner is our favorite runner, it is used for all Environments and is therefore in all bottles created, but also for wineprefixes imported into Bottles. We offer 2 different builds:

* [chardonnay](https://github.com/bottlesdevs/wine) \(our runner, available by default in Bottles v3\)
* lutris

Includes patches from wine-staging and lutris, which increases support for compatible Windows applications.

The **Proton** runner \(developed by [Valve](https://github.com/ValveSoftware/Proton) and improved/offered by [GloriousEggroll](https://github.com/GloriousEggroll/proton-ge-custom) in the GE custom version\) is a much more complex version of Wine and is suitable for the most modern games.

It contains several patches for specific gaming titles support, implements [OpenVR](https://partner.steamgames.com/doc/features/steamvr/openvr) support and integrates dxvk \(installable on wine from the bottle preferences page\).

The Proton runner can be installed from the Bottles Preferences page and choosen on bottle creation selecting the Custom Environment. You can also switch from Wine to Proton at any time by changing your bottle preferences.

{% hint style="warning" %}
We personally recommend using the Proton runner only in special cases where there is a patch for a specific video game. However, **Valve collaborates in the development of Wine** and many of the features integrated into Proton are also available in the latest versions of Wine.
{% endhint %}

## Runner updates

You can install new runners in one click from Bottles Preferences.

![Runners management from Bottles Preferences page.](../.gitbook/assets/screenshot-from-2021-01-05-18-58-16.png)

If you're feeling fearless, you can enable Release Candidates to download and then test premature versions of Wine, which may include greater software compatibility at the cost of bugs and possible regressions.

![Enable Release Candidate from Runners preferences in the General tab.](../.gitbook/assets/screenshot-from-2021-01-05-19-36-11.png)

