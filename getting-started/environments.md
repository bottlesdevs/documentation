---
description: Bottles use environments for creating new bottles.
---
# Environments

Environments offer pre-made configurations to enhance support for specific types of Windows apps.

Bottles offer the following default environments:

* **Gaming** for games
* **Application** for applications
* **Custom** is a clean environment for experimenting with different configurations.

![Environment selection](<../.gitbook/assets/getting_started/environments/Custom.png>)

### Gaming environment

This environment comes with the Soda runner, with DXVK and VKD3D for translating DirectX 9 to 12 games to Vulkan. Direct access to NVIDIA GPUs through NVAPI is also supported. The environment uses dedicated graphics cards (called in-app as `Discrete graphics`) to enhance performance on devices with multiple GPUs. By default, Esync is used to synchronize and improve performance, though on supported kernels, you should switch this to Fsync for better results.

You can use LatencyFleX to reduce input lag. DLSS (NVIDIA GPUs only), FidelityFX, and vkBasalt post-processing can be configured to further enhance performance. You can also set GameMode and game file preloading for this.

### Application environment

This environment is a less intensive version of the gaming environment. Hardware acceleration is supported to ensure a seamless multimedia experience. Common fonts are preinstalled and Wine's Mono is installed in place of the .NET Framework.

### Custom environment

This is a clear environment where you can experiment, test and configure your bottle. You can also choose which runner to use for your experiments, just install more from the preferences page.

## Environment preferences

Regardless of the environment you choose, you can change your preferences at any time, e.g. change the type of synchronisation or add and remove dependencies.