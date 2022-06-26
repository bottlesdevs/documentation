# Can't enable Steam Proton manager

Starting from version 2022.6.28, Bottles allows you to manage Steam Proton prefixes by enabling the setting of the same name.&#x20;

If you have installed Bottles via Flatpak, it is essential to give it permissions to access the Steam path, otherwise the integration will not be activated.

Proceed according to your Steam installation.

#### Steam non-Flatpak

```
flatpak override com.usebottles.bottles --filesystem=xdg-data/Steam
```

#### Steam Flatpak

```
flatpak override com.usebottles.bottles --filesystem=~/.var/app/com.valvesoftware.Steam/data/Steam
```

then restart Bottles.
