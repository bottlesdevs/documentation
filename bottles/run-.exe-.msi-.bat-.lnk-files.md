---
description: There are two ways to start these executables in Bottles
---

# Run .exe/.msi/.bat/.lnk files

An executable can be used to start or install a program in a bottle. In Bottles you can run these files in two ways:

* from the **GUI** using the **Run executable** feature
* using the **CLI** (this can be useful if you don't want to show Bottles GUI)

### Launch from GUI

Let's go into the details of the bottle of our interest (read [here](https://docs.usebottles.com/getting-started/first-run#your-first-bottle) how to create one if you don't have one).

Under the bottle name we find the **Run executable** button:

![Bottle details - Run executable](<../.gitbook/assets/image (31).png>)

Pressing it will open a window from which to select the executable of our interest, once selected it will be executed in the bottle.

#### Launch with arguments

Some applications require you to start with arguments. As you can see from the previous image, next to Run executable there is an arrow, by pressing it you can select the item Run with arguments. Once pressed, a screen will appear where you can enter our arguments:

![Bottles details - Run executable with arguments](<../.gitbook/assets/image (32).png>)

Once finished, we press on Run and select the executable to start it in the bottle.

### Launch from CLI (supports .lnk)

To start an executable from the CLI, we can proceed in two ways.

Simply **passing the path of the executable** to the command to start Bottles, the GUI will appear asking which bottle to start it. It is also possible to tell Bottles from the preferences to close automatically after starting the executable.

{% hint style="warning" %}
The following statement is for the Unstable version of Bottles only and will be officially implemented in version 2021.7.28.
{% endhint %}

Otherwise you can avoid the GUI by specifying the parameters:

{% tabs %}
{% tab title=".EXE/.MSI/.BAT" %}
```bash
bottles -b bottle_name -e /full/executable/path
```

| parameter         | hint                                               | required |
| ----------------- | -------------------------------------------------- | -------- |
| `-b --bottle`     | the bottle name                                    | ✅        |
| `-e --executable` | the executable full path (supports .exe/.msi/.bat) | ✅        |
{% endtab %}

{% tab title=".LNK" %}
```bash
bottles -b bottle_name -l /full/lnk/path
```

| parameter     | hint              | required |
| ------------- | ----------------- | -------- |
| `-b --bottle` | the bottle name   | ✅        |
| `-l --lnk`    | the lnk full path | ✅        |
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Note: use `flatpak run com.usebottles.bottles` instead of `bottles` for flatpak.
{% endhint %}

In this way the Bottles GUI will not be displayed, useful if we want to create custom Desktop Entry to start our favorite applications.
