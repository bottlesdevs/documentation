---
description: Using Bottles via xdg-open
---

# xdg-open links

Since the [2022.5.28 Release](https://usebottles.com/blog/release-2022.5.28/), Bottles support the launch programs using links with special Bottles’ protocol. Such links will be recognized by the **xdg-open** utility and redirected to Bottles to execute certain commands.

### xdg-open syntax

**xdg-open** command opens a file or URL in the user's preferred application. General syntax:

`xdg-open {file | URL}`

### Bottles URL syntax

The link to run the program in a bottle has the following syntax:

`bottles:run/<bottle>/<program>`

Where

`<bottle>` is the name of the bottle (displayed in the interface, or the _"Name"_ parameter in _bottle.yml_);

`<program>` is the name of the program for launch (displayed in the interface, or the _"name"_ parameter of the corresponding program in _bottle.yml_).

### Usage

For example, to run the program **"Notepad"** in the bottle **"MyLittleBottle"**, the full **xdg-open** command will look like this:

`xdg-open bottles:run/MyLittleBottle/Notepad`

Or you can just use the `bottles:run/MyLittleBottle/Notepad` URL in your browser.