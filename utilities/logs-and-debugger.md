---
description: Whether you are a developer or a log-hunting user, debugging is the way to go.
---
# Logs & Debugger

There are two way to catch out the logs from Bottles:

* using your System Terminal
* using the Wine Debugger Console

Let's face them both together.

## System Terminal

To capture all Bottles and wineprefixes logs, just start Bottles itself through the Terminal installed on the system, for example through:

* GNOME Terminal
* Konsole
* XFCE4 Terminal
* MATE Terminal
* xterm
* etc.

For example, if you installed Bottles via AppImage:

```bash
cd /path_to_appimage
./Bottles*.AppImage
```

This way you will receive all the logs in the Terminal (which must remain open).

![Example of Bottles log in System Terminal.](../.gitbook/assets/screenshot-from-2021-01-05-23-32-13.png)

### Logging levels

Using this method you will also see logs from Bottles and not only from runners. The following are the logging levels to better read and understand logs:

* **\[INFO] **This log informs the correct functioning of one or more operations performed by Bottles.
* **\[WARNING] **It is shown when an operation has been performed but there are one or more non-blocking warnings.
* **\[ERROR] **An error occurred and the operation was not completed.
* **\[CRITICAL] **The sudden error may have jeopardized Bottles from functioning correctly or an exception was not handled.

## Wine Debugger

Wine comes with a built-in debugger (`winedbg`) for analyzing processes running in a wineprefix.

Wine debugger has several useful abilities, including the one to generate backtraces, set breakpoints, and even disassemble code. It supports a subset of the gdb commands, especially the most common ones. For instance you can use info proc and info thread and then attach to a given process, which can be very useful for running backtraces on deadlocks.

From: [WineHQ Wiki](https://wiki.winehq.org/Winedbg).

### Attach to a process

{% hint style="info" %}
The Wine debugger allows us to access the backtrace of a crashed or frozen process, when this is not normally offered.
{% endhint %}

First run a Windows executable file in your bottle, then launch `winedbg` using the **Debug** voice in the Utility section from your bottle details.

![Bottle - Wine Debugger](<../.gitbook/assets/image (29).png>)

The system Terminal will run with `winedbg` running inside your bottle.

#### Backtrace for all running processes

To get the backtrace of all running processes in the wineprefix, type:

```bash
bt all
```

#### Backtrace from specific process

To receive the backtrace of a specific process, type:

```
info process
```

to list all active processes in the wineprefix.

```bash
Wine-dbg>info process
 pid      threads  executable (all id:s are in hex)
 0000010c 2        'conhost.exe'
 000000fc 1        'npp.7.9.2.Installer.exe'
 00000060 3        'explorer.exe'
 00000038 7        'services.exe'
 000000cc 6        \_ 'rpcss.exe'
 000000a4 3        \_ 'svchost.exe'
 00000080 5        \_ 'winedevice.exe'
 00000068 5        \_ 'plugplay.exe'
 00000044 4        \_ 'winedevice.exe'

```

Focus on the first column of the output where the process ID appears, let's attach the debugger to the process ID of interest:

```bash
Wine-dbg>attach 0x<pid> # where <pid> is the ID of our interest
```

This will give us the backtrace of the program if already crashed. Otherwise we can get it immediately by typing:

```bash
set $BreakOnFirstChance=0
cont
```

so keep using the program and on crash go back to Terminal to check the backtrace.
