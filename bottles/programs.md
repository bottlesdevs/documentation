---
description: Find and launch all the programs installed in your bottles in one click.
---
# Programs

{% hint style="warning" %}
While stable, this feature is still under development.
{% endhint %}

Bottles searches the bottle for the installed software and places them in the programs section of the bottle.

The search is done through the common Start Menu directories, Bottles looks for all the `.lnk` files in these directories and extracts some information such as: name of the application and path of the executable.

### Launch installed programs

After installing a software application in the bottle, just go to the Programs section to start it.

![Bottles - Programs](<../.gitbook/assets/image (33).png>)

If you don't see the program you are looking for, press the Refresh button at the top right to let Bottles searching for new programs.

Then press the Play button on the right to start the program.

#### Custom arguments

Some programs may require arguments to be passed to the executable. To set them you can press the context menu (the icon with the 3 dots) and choose Change Launch Options.

![Bottles - Programs - Change Launch Options](<../.gitbook/assets/image (34).png>)

A field will appear where you can enter the arguments of the executable, once done press Save at the top right and start the program. Bottles will remember the arguments for that executable, so you don't have to add them again.

![Bottles - Programs - Launch Options](<../.gitbook/assets/image (35).png>)

#### Prefix and suffix in launch options

The `%command%` placeholder can be used in the Launch Options to customize prefixes and suffixes:

```bash
my_command %command% -flag1 -flag2
```

#### The program does not appear

If the program does not appear in the list even after the Refresh, it may be that it is installed in a path not monitored by Bottles. [Open an issue](https://github.com/bottlesdevs/Bottles/issues/new/choose) so that we can identify the path and add it to the list of directories.
