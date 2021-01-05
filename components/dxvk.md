---
description: 'Vulkan-based implementation of D3D9, D3D10 and D3D11 for Wine.'
---

# DXVK

This magical component takes care of translating instructions from Direct3D 9/10/11 \(from Windows\) to Vulkan \(to Linux\) and is developed by [doitsujin](https://github.com/doitsujin/dxvk) and many other contributors.

Mainly dxvk is a .dll override bundle which, integrated in a wine prefix, allows you to detect and translate calls from DirectX to Vulkan. This is done automatically, without any user intervention.

## How to enable

Basic DXVK is installed and enabled by Bottles when creating a bottle in the following environments:

* Gaming environment
* Software environment

You can check its activation from the bottle preferences, checking the "DXVK for Direct3D" voice.

When this component is enabled, a backup of the old dlls is created in the wineprefix and automatically recovered when disabled.

## DXVK updates

You can keep this component updated from Bottles preferences.

![DXVK management from Bottles Preferences page.](../.gitbook/assets/screenshot-from-2021-01-05-19-30-20.png)

