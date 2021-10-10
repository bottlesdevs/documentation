---
description: Your first experience with Bottles starts here.
---
# First run

At the first start you will be shown the Onboard, which is a wizard that will explain some concepts and help you configure Bottles.

![Bottles Onboard](<../.gitbook/assets/image (5).png>)

Once the key concepts of Bottles have been introduced, a runner (\~ 70MB) will be downloaded, which is necessary for creating your bottles.

**The files we download are available from our **[**public repository**](https://github.com/bottlesdevs/components)** for analysis purposes.** Below is the list of files that we are going to download at the first start:

* the latest Vaniglia runner ([**vaniglia-6.11**](https://github.com/bottlesdevs/components/blob/main/runners/wine/vaniglia-6.11.yml)** **at time of writing)
* the latest DXVK ([**dxvk-1.9**](https://github.com/bottlesdevs/components/blob/main/dxvk/dxvk-1.9.yml) at time of writing)

**each file is checked with the repository checksum**, if this check fails, the file is deleted and the installation fails.

{% hint style="info" %}
We cannot offer these files with Bottles as these have different release cycles.

**It is not our limit, it is how it must be done.** Downloading these files with the package means increasing the release frequency (even several times a day) or providing Bottles with older versions of these components. What we have chosen is the correct way to be able to offer the same experience to all distribution formats and to ensure that we offer the latest version of the components to the user on first launch.
{% endhint %}



![Downloading the first runner](<../.gitbook/assets/image (6).png>)

This is a one time operation, you can use the same runner for all your bottles or install others from the Bottles preferences.

Finally everything is ready and you can start using Bottles!

![Everything is ready!](<../.gitbook/assets/image (7).png>)

## Offline? You do not have time?

Are you offline or don't want to download it now? No problem.

If you are Offline, Bottles will notice and ask you to go online to proceed. All features that require a connection are blocked and will be active again as soon as you come back online!

You can go to the Bottles Preferences at any time and install a runner. Alternatively, when you create a bottle, you will be automatically taken to the installation page.

![Wine Runners Preferences](<../.gitbook/assets/image (9).png>)

### Your first Bottle

When everything is ready, you will be faced with a screen like the following, telling you that there is no bottles yet.

![Empty bottles view](<../.gitbook/assets/image (10).png>)

To create your first bottle, you will need to press the plus button on the top left and proceed following the on-screen instructions.

![](<../.gitbook/assets/image (11).png>)

Bottles uses an ad environments system for its bottles, I suggest you continue reading the next section for more information.
