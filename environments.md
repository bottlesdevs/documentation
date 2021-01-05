---
description: In Bottles we use environments for creating new bottles.
---

# Environments

The Bottles Environments offers a bundle of configurations, dependencies to increase support for Windows software in certain contexts.

We offer the following Environments:

* **Gaming** for games
* **Software** for.. software
* **Custom** is just a clean space where you can start making experiments

![Environment selection.](.gitbook/assets/screenshot-from-2021-01-05-13-45-34.png)

{% hint style="info" %}
Bottles dependency support is still young, at the moment the Environments do not install dependencies but you can do it yourself from the Dependencies tab in the detail of your bottle.
{% endhint %}

### Gaming environment

This environment comes with the following configuration:

* dxvk enabled
* Esync enabled
* Discrete Graphics Card enabled \(useful for laptops with hybrid graphics setup\)
* PulseAudio latency forced to 60ms for better audio quality in-game

### Software environment

This environment enables dxvk by default, ensuring support for multimedia applications \(such as 3D modeling, Video Edting and drawing programs\) but also office and productivity software.

### Custom environment

If you are a nerd \(even more nerd\) then this is the environment for you! 

This is a clean environment where you can experiment, test and configure your bottle! You can also choose the runner to use for your experiments, just install others from Bottles Preferences page.

Pssst ...! If you enable the Experimental Features in Bottles preferences page, you can try the versioning feature. This \(unstable at the moment, so expect bugs, spiders and monsters under the bed ..\) allows you to create versioned botles, keeping track of changes, creating restore points and obviously restoring to a previous state!

## Environment preferences

Regardless of the environment you choose, you can change your preferences at any time, enable/disable dxvk, esync, fsync, etc.

