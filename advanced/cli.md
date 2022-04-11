---
description: Using Bottles via CLI
---

# CLI

In 2022.3.28 we have introduced a new CLI interface, which provide more features then the prior.

### Launch CLI

The new interface has a dedicated command: `bottles-cli` .

If using Bottles as Flatpak (the suggested way), launch it with:

```
flatpak run --command=bottles-cli com.usebottles.bottles --help
Bottles is a tool to manage your bottles

positional arguments:
  {info,list,programs,tools,reg,edit,new,run}
                        sub-command help
    info                Show information about Bottles
    list                List entities
    programs            List programs
    tools               Launch WINE tools
    reg                 Manage registry
    edit                Edit a bottle configuration
    new                 Create a new bottle
    run                 Run a program

optional arguments:
  -h, --help            show this help message and exit
  -v, --version         show program's version number and exit
  -j, --json            Outputs in JSON format
```

for all other packages:

```
bottles-cli --help
```

### Interfaces/Arguments

Since Bottles has a lot of features, to keep things organized we have divided it in multiple interfaces: info, list, programs, tools, reg, edit, new, run.

#### Info

The `info` interface can be used to access Bottles information:

```
usage: bottles-cli info [-h] {bottles-path,health-check}

positional arguments:
  {bottles-path,health-check}
                        Type of information

optional arguments:
  -h, --help            show this help message and exit
```

#### List

The `list` command is meant to be used for listing Bottles stuff:

```
usage: bottles-cli list [-h] [-f FILTER] {bottles,components}

positional arguments:
  {bottles,components}  Type of entity

optional arguments:
  -h, --help            show this help message and exit
  -f FILTER, --filter FILTER
                        Filter bottles and components (e.g. '-f 'environment:gaming')
```

the `-f` argument for `bottles` supports the `environment` prefix:

```
bottles-cli list bottles -f environment:gaming
```

while for `components` the `category` one can be used:

```
bottles-cli list components -f category:dxvk
```

#### Programs

The `programs` interface can be used to list all programs in a bottle (only added by users or installers).

```
usage: bottles-cli programs [-h] -b BOTTLE

optional arguments:
  -h, --help            show this help message and exit
  -b BOTTLE, --bottle BOTTLE
                        Bottle name
```

#### Tools

The `tools` interface can be used to launch any WINE utility.

```
usage: bottles-cli tools [-h] -b BOTTLE {cmd,winecfg,uninstaller,regedit,taskmgr,control,explorer}

positional arguments:
  {cmd,winecfg,uninstaller,regedit,taskmgr,control,explorer}
                        Tool to launch

optional arguments:
  -h, --help            show this help message and exit
  -b BOTTLE, --bottle BOTTLE
                        Bottle name
```

#### Reg

The `reg` interface can be used to access and edit the bottle's Windows registry.

```
usage: bottles-cli reg [-h] -b BOTTLE -k KEY -v VALUE [-d DATA] [-t {REG_DWORD,REG_SZ,REG_BINARY,REG_MULTI_SZ}] {add,edit,del}

positional arguments:
  {add,edit,del}        Action to perform

optional arguments:
  -h, --help            show this help message and exit
  -b BOTTLE, --bottle BOTTLE
                        Bottle name
  -k KEY, --key KEY     Registry key
  -v VALUE, --value VALUE
                        Registry value
  -d DATA, --data DATA  Data to be set
  -t {REG_DWORD,REG_SZ,REG_BINARY,REG_MULTI_SZ}, --key-type {REG_DWORD,REG_SZ,REG_BINARY,REG_MULTI_SZ}
                        Data type
```

#### Edit

The `edit` interface can be used to edit a bottle (e.g. any parameter, environment variables, Windows version, runner, dxvk, vkd3d..).

```
usage: bottles-cli edit [-h] -b BOTTLE [--params PARAMS] [--env-var ENV_VAR] [--win WIN] [--runner RUNNER] [--dxvk DXVK] [--vkd3d VKD3D] [--nvapi NVAPI] [--latencyflex LATENCYFLEX]

optional arguments:
  -h, --help            show this help message and exit
  -b BOTTLE, --bottle BOTTLE
                        Bottle name
  --params PARAMS       Set parameters (e.g. '-p dxvk:true')
  --env-var ENV_VAR     Add new environment variable (e.g. '-env-var WINEDEBUG=-all')
  --win WIN             Change Windows version (e.g. '--win win7')
  --runner RUNNER       Change Runner (e.g. '--runner caffe-7.2')
  --dxvk DXVK           Change DXVK (e.g. '--dxvk dxvk-1.9.0')
  --vkd3d VKD3D         Change VKD3D (e.g. '--vkd3d vkd3d-proton-2.6')
  --nvapi NVAPI         Change DXVK-Nvapi (e.g. '--nvapi dxvk-nvapi-1.9.0')
  --latencyflex LATENCYFLEX
                        Change LatencyFleX (e.g. '--latencyflex latencyflex-v0.1.0')
```

#### New

The `new` interface can be used to create a new bottle.

```
usage: bottles-cli new [-h] --bottle-name BOTTLE_NAME --environment ENVIRONMENT [--custom-environment CUSTOM_ENVIRONMENT] [--arch ARCH] [--runner RUNNER] [--dxvk DXVK] [--vkd3d VKD3D] [--nvapi NVAPI] [--latencyflex LATENCYFLEX]

optional arguments:
  -h, --help            show this help message and exit
  --bottle-name BOTTLE_NAME
                        Bottle name
  --environment ENVIRONMENT
                        Envorinment to apply (gaming|application|custom)
  --custom-environment CUSTOM_ENVIRONMENT
                        Path to a custom environment.yml file
  --arch ARCH           Architecture (win32|win64)
  --runner RUNNER       Name of the runner to be used
  --dxvk DXVK           Name of the dxvk to be used
  --vkd3d VKD3D         Name of the vkd3d to be used
  --nvapi NVAPI         Name of the dxvk-nvapi to be used
  --latencyflex LATENCYFLEX
                        Name of the latencyflex to be used
```

#### Run

The `run` interface can be used to launch an executable from a given path or any program in a bottle using its name:

```
usage: bottles-cli run [-h] -b BOTTLE [-e EXECUTABLE] [-a ARGS] [-p PROGRAM]

optional arguments:
  -h, --help            show this help message and exit
  -b BOTTLE, --bottle BOTTLE
                        Bottle name
  -e EXECUTABLE, --executable EXECUTABLE
                        Path to the executable
  -a ARGS, --args ARGS  Arguments to pass to the executable
  -p PROGRAM, --program PROGRAM
                        Program to run
```

### Developers mode

We've added a `--json` global argument to help developers accessing stuff from the Bottles' CLI. It can be used with any interface and will return the output in JSON format. Some examples:

```
bottles-cli --json info health-check
{"Display": {"X.org": true, "X.org (port)": ":99.0", "Wayland": false}, "Graphics": {"vendors": {"nvidia": {"vendor": "nvidia", "envs": {"__NV_PRIME_RENDER_OFFLOAD": "1", "__GLX_VENDOR_LIBRARY_NAME": "nvidia", "__VK_LAYER_NV_optimus": "NVIDIA_only"}, "icd": "/usr/lib/x86_64-linux-gnu/GL/vulkan/icd.d/nvidia_icd.json:/usr/lib/i386-linux-gnu/GL/vulkan/icd.d/nvidia_icd.json"}, "amd": {"vendor": "amd", "envs": {"DRI_PRIME": "1"}, "icd": "/usr/lib/x86_64-linux-gnu/GL/vulkan/icd.d/radeon_icd.x86_64.json:/usr/lib/i386-linux-gnu/GL/vulkan/icd.d/radeon_icd.i686.json"}}, "prime": {"integrated": {"vendor": "amd", "envs": {"DRI_PRIME": "1"}, "icd": "/usr/lib/x86_64-linux-gnu/GL/vulkan/icd.d/radeon_icd.x86_64.json:/usr/lib/i386-linux-gnu/GL/vulkan/icd.d/radeon_icd.i686.json"}, "discrete": {"vendor": "nvidia", "envs": {"__NV_PRIME_RENDER_OFFLOAD": "1", "__GLX_VENDOR_LIBRARY_NAME": "nvidia", "__VK_LAYER_NV_optimus": "NVIDIA_only"}, "icd": "/usr/lib/x86_64-linux-gnu/GL/vulkan/icd.d/nvidia_icd.json:/usr/lib/i386-linux-gnu/GL/vulkan/icd.d/nvidia_icd.json"}}}, "Kernel": {"Type": "Linux", "Version": "5.16.15-201.fc35.x86_64"}, "Distro": {"Name": "GNOME", "Version": "\"42 (Flatpak runtime)\""}, "Tools": {"cabextract": true, "p7zip": true, "patool": true, "glibc_min": "2.33"}, "Bottles_envs": null}

bottles-cli --json list components -f category:runners
{"runners": ["vaniglia-7.5", "sys-wine-7.0", "caffe-7.5", "caffe-7.1"]}
```

in some cases it will return more info then the classic launch, e.g. for the `programs` interface:

```
bottles-cli --json programs -b MyBottle
[{"executable": "Battle.net.exe", "arguments": "", "name": "Battle.net", "path": "C:\\Program Files (x86)\\Battle.net\\Battle.net.exe", "folder": "", "icon": "", "script": null, "removed": null}, {"executable": "EpicGamesLauncher.exe", "arguments": "-opengl -SkipBuildPatchPrereq", "name": "Epic Games Store", "path": "C:\\Program Files (x86)\\Epic Games\\Launcher\\Portal\\Binaries\\Win32\\EpicGamesLauncher.exe", "folder": "", "icon": "", "script": null, "removed": null}, {"executable": "GalaxyClient.exe", "arguments": "--in-process-gpu /runWithoutUpdating /deelevated", "name": "GOG Galaxy", "path": "C:\\Program Files (x86)\\GOG Galaxy\\GalaxyClient.exe", "folder": "", "icon": "", "script": null, "removed": null}]
```
