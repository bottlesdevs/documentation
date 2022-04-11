---
description: In Bottles we use environments for creating new bottles.
---
# Environments

Bottles Environments offers a package of configurations and dependencies to enhance support for Windows software in some contexts.

We offer the following default Environments:

* **Gaming** for games
* **Application** for... applications
* **Custom** is just a clear workspace where you can start making experiments

![Environment selection](<../.gitbook/assets/getting_started/environments/Custom.png>)

### Gaming environment

This environment comes with the following configuration:

* DXVK enabled
* VKD3D disabled
* Esync enabled
* Discrete Graphics Card enabled (useful for laptops with hybrid graphics setup)
* PulseAudio latency forced to 60ms for better audio quality in-game
* d3dx9, d3dcompiler_43, d3dcompiler_47 dlls
* Microsoft Line Services
* Arial, Times and Courier fonts

### Application environment

This environment enables DXVK and VKD3D by default, ensuring support for multimedia applications (such as 3D modeling, Video Editing and drawing programs) but also office and productivity software. It will also install Arial, Times and Courier fonts, and the Wine mono, replacing the .NET Framework.

### Custom environment

If you are a nerd (even more nerd) then this is the environment for you! 

This is a clear environment where you can experiment, test and configure your bottle! You can also choose which runner to use for your experiments, just install more from the Bottles Preferences page.

## Environment preferences

Regardless of the environment you choose, you can change your preferences at any time, e.g. change the type of synchronisation or add and remove dependencies.
