---
description: Your first experience with Bottles starts here.
---

# First run

At first run, you will see the Onboard, a wizard that explains necessary concepts and helps you set up Bottles.

![Bottles - Welcome](<../.gitbook/assets/getting_started/first_run/Welcome.png>)

Additional packages (around 90 MB) will be downloaded after you finish the wizard. These packages are necessary to create a bottle.

**These packages are available in our [public repository](https://github.com/bottlesdevs/components) for anyone to analyze.** At first run, Bottles will download these packages:

* Soda runner (around 60 MB)
* DXVK (around 8 MB)
* VKD3D (around 2 MB)
* NVAPI (around 2 MB)
* LatencyFleX (around 500 KB)
* Runtime (around 16 MB)

**Bottles verifies these packages through checksums provided by the repository.** If the verification fails, the file is deleted and Bottles will try to download a clean, untampered file again.

{% hint style="info" %}
Bottles cannot be distributed with these packages since these packages have different release cycles.

**We do this to provide Bottles users with the most seamless installation experience.** If Bottles bundle these packages, we will need to either update our app in Flathub several times a week, or bundle an outdated package.

Thus, we have decided to use this distribution method to ensure everyone can access the latest packages without complicated app updates and to make sure first-time users can get a seamless setup experience with the latest packages.
{% endhint %}

![Downloading the first runner](<../.gitbook/assets/getting_started/first_run/Downloading.png>)

These packages are only downloaded once. You can reuse the runner and other libraries on all your bottles, and install alternatives through the preferences menu.

Everything is ready and you can now create your first bottle!

![Everything is ready!](<../.gitbook/assets/getting_started/first_run/Ready.png>)

Below is a video showing the process of first boot, first bottle creation and running a Windows app.

{% embed url="https://www.youtube.com/watch?feature=youtu.be&v=JQyOGtPQ644" %}

## Offline? You do not have time?

Are you offline or don't want to download it now? No problem.

If you are offline, Bottles will detect it and ask you to go online to continue. You will temporarily be unable to access features that need the internet. These features will reactivate as soon as you go back online.

You can go to the preferences menu anytime to install a runner. You will also be automatically taken to the installation page when you create a bottle.

![Bottles - Preferences - Runners](<../.gitbook/assets/components/runners/Main.png>)

### Your first bottle

After setup, you will see the following screen, indicating that there are no bottles yet.

![Empty bottles view](<../.gitbook/assets/getting_started/first_run/NoBottles.png>)

To create your first bottle, press the + button on the top left and follow the on-screen instructions.

![Bottle creation](<../.gitbook/assets/getting_started/first_run/NewBottle.png>)

You can learn more about different types of bottles in the next section.