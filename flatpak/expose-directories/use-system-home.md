---
description: How to use the system home and not the sandboxed one
---
# Use system home

{% hint style="warning" %}
Warning, this procedure can expose your system (and therefore your personal files) to dangers, as we are going to break the Bottles sandbox.
{% endhint %}

### What's the homedir?

Each user has a personal homedir (`/home/your_username`), this is the place when you can store your personal files, like videos, photos or documents. This path is also used for cache files `.cache` and software configurations `.config`.

#### How runners use my homedir?

Each [runner](../../components/runners.md) when make a new windows prefix (we call these bottles here), create a similar Windows structure:

```
._ bottles/
    |_ your_bottle/
        |_ bottle.yml
        |_ drive_c/
            |_ ProgramData/
            |_ Program Files/
            |_ Program Files (x86)/
            |_ users/
                |_ Public/
                |_ your_username/
            |_ windows/
```

It generate a folder in the `users/` path, for the current logged in user (e.g. I'm currently logged as `mirko`, so the runner will create a `mirko/` folder inside `users/`. It also create a Public folder but it is not our interest right now.

Each user folder contains some symlink to the original homedir:

```
..
    |_ users/
        |_ mirko
            |_ AppData
            |_ Contacts
            |_ Desktop -> ~/Desktop
            |_ Documents -> ~/Documents
            |_ Downloads -> ~/Downloads
            |_ Favorites
            |_ Links
            |_ Music -> ~/Music
            |_ Pictures -> ~/Pictures
            |_ Saved Games
            |_ Searches
            |_ Temp
            |_ Videos -> ~/Videos
```

So each program installed in the bottle, can see your files from the linked folders.

### Sand-boxed userdir (homedir)

Starting from Bottles 2021.10.14, the userdir path is sand-boxed, so the above symlinks doesn't exists.

Creating a new bottle, Bottles detect if it is running under Flatpak, then remove these symlinks and make them as normal folders inside the bottle. As a result, each program can only works with files inside the sand-boxed userdir (sharable across programs).

#### How to revert this?

While <mark style="color:red;">**this is a practice discouraged by Bottles and we take no responsibility for what may happen after exposing your homedir to the runner**</mark>, there is a very simple way to do it.

First we need to expose the homedir to Bottles, giving it the right permission ([read here](./) how to achieve this). Once the homedir is exposed, get into a terminal and move to the Bottles flatpak path:

```
cd ~/.var/app/com.usebottles.bottles/data/bottles/bottles
```

then find the bottle you want to give access to the homedir (e.g. it is called Testing in our case), so move to the userdir:

```
cd Testing/drive_c/users/your_username/ && ls -l
```

remove the folders you want to expose (e.g. Documents):

```
rm -r Documents
```

then recreate as symlink (e.g. for Documents):

```
ln -s ~/Documents Documents
```

and this is all!
