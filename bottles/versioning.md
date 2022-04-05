---
description: Keep your data safe, reduce the risk of compromising them and restore the status of the bottles in one click.
---
# Versioning


The third version of Bottles (Treviso) introduced a new feature called Versioning. 

This is a versioning system for your bottles, based on user-defined restore points, allowing you to restore the bottle to a previous state when something goes wrong. Useful if you are testing multiple configurations. 

### How versioning works

Versioning works through recovery points called states. The first recovery point is used as an index of the bottle files. Whenever a new state is created, Versioning checks the differences between the current files and those in the index of the previous state (by checking the checksums of the new, missing and updated files). When it detects changes, they are recorded in the index of the new state.

Below is an example of a state index created after installing the Comic font in the bottle:

```
{
    "Update_Date": "2021-07-02 21:52:18.906569",
    "Additions": [
        {
            "file": "windows/Fonts/Comic.TTF",
            "checksum": "a50f9c96a76356e3d01013e0b042989f"
        },
        {
            "file": "windows/Fonts/ComicBD.TTF",
            "checksum": "81d64ec3675c4adc14e9ad2c5c8103a7"
        }
    ],
    "Removed": [],
    "Changes": []
}
```

As we can see, Versioning detected the presence of new files and added them to the index. If we restore the previous state to the one just created, the Comic font will be removed.

Each state requires a comment during creation (it will be used to recognize it when necessary), and the creation date is also saved to provide more details to the user.

The currently active state is highlighted in purple.

![Bottle - Versioning - Active state](../.gitbook/assets/bottles/versioning/Main.png)

To restore a state it is necessary to press the icon with the clock to the right of the desired state.

### How to use versioning

You can use versioning with a new bottle or an existing one.

#### On bottle creation

The versioning is available during the creation of the bottle, only if you select the "Custom" environment, then checking "Use versioning" from the Advanced options.

![Bottle - Versioning on Custom environment](../.gitbook/assets/bottles/versioning/NewBottle.png)

In this way, a restore point will be created as soon as the bottle is created and versioning will take effect.

#### In existing bottles

Versioning can be enabled for any existing bottle by simply selecting the Versioning section in the bottle details and creating a new state that will be used as the bottle's initial index.

![Bottle - Versioning - First state](../.gitbook/assets/bottles/versioning/ExistingBottle.png)

We can understand if versioning on a bottle is active, through the purple icon in the bottle list and in the detail of the same, this also shows the number of the current state.

![Bottles List](../.gitbook/assets/bottles/versioning/BottlesList.png)