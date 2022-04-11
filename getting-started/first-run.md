---
description: Your first experience with Bottles starts here.
---

# First run

At the first start you will be shown the Onboard, which is a wizard that will explain some concepts and help you configure Bottles.

![Bottles - Welcome](<../.gitbook/assets/getting_started/first_run/Welcome.png>)

Once the key concepts of Bottles have been introduced, some important stuff (\~ 70MB) will be downloaded, which is necessary for creating your bottles.

**The files we download are available from our** [**public repository**](https://github.com/bottlesdevs/components) **for analysis purposes.** The latest versions of the following components will be downloaded at the first start:


* Caffe runner
* DXVK
* VKD3D
* NVAPI
* LatencyFleX
* Runtime 

**Each file is checked with the repository checksum**, if this check fails, the file is deleted and the installation fails.

{% hint style="info" %}
We cannot offer these files with Bottles as these have different release cycles.

**It is not our limit, it is how it must be done.** Downloading these files with the package means increasing the release frequency (even several times a day) or providing Bottles with older versions of these components. What we have chosen is the correct way to be able to offer the same experience to all distribution formats and to ensure that we offer the latest version of the components to the user on first launch.
{% endhint %}

![Downloading the first runner](<../.gitbook/assets/getting_started/first_run/Downloading.png>)

This is a one time operation, you can use the same runner for all your bottles or install others from the Bottles preferences.

Finally everything is ready and you can start using Bottles!

![Everything is ready!](<../.gitbook/assets/getting_started/first_run/Ready.png>)

Below is a video showing the process of first boot, first bottle creation and running a Windows program.

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=JQyOGtPQ644" %}

## Offline? You do not have time?

Are you offline or don't want to download it now? No problem.

If you are Offline, Bottles will notice and ask you to go online to proceed. All features that require a connection are blocked and will be active again as soon as you come back online!

You can go to the Bottles Preferences at any time and install a runner. Alternatively, when you create a bottle, you will be automatically taken to the installation page.

![Bottles - Preferences - Runners](<../.gitbook/assets/components/runners/Main.png>)

### Your first Bottle

When everything is ready, you will be faced with a screen like the following, telling you that there is no bottles yet.

![Empty bottles view](<../.gitbook/assets/getting_started/first_run/NoBottles.png>)

To create your first bottle, you will need to press the plus button on the top left and proceed following the on-screen instructions.

![Bottle creation](<../.gitbook/assets/getting_started/first_run/NewBottle.png>)

You can read more about the different types of bottles in the next section.
