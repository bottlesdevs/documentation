---
description: Propose new dependencies to the Bottles community
---

# Missing dependencies

Our dependency system is very young and still has a long way to go. But we can all make this a way better, together! Help us expand and improve the Bottles dependency system.

{% hint style="info" %}
This page is only a first reference. Please refer to the [dedicated documentation](https://maintainers.usebottles.com/dependencies/Introduction).
{% endhint %}

### First the basics

All dependencies present in Bottles are placed in a public repository, available [here](https://github.com/bottlesdevs/dependencies).

The repository consists of 3 main points:

* the `index.yml` file that is the index of all dependencies available in the repository
* the **Essentials** and **Fonts** **categories** (in the future there will be more) where all the dependencies manifests are collected
* the dependency manifest

The index.yml file looks like:

```yaml
vcredist2013:
  Description: Microsoft Visual C++ Redistributable (2013) 12.0
  Category: Essentials
vcreditst2015:
  Description: Microsoft Visual C++ Redistributable (2015)
  Category: Essentials
vcredist2019:
  Description: Microsoft Visual C++ Redistributable (2015-2019) 14.28.29325
  Category: Essentials
```

How you can see, every dependency is index with it's name, the description and the category where it is located.

Each dependency has a manifest that contains some information and instructions for its installation. This is an example from [Fonts/allfonts.yml](https://github.com/bottlesdevs/dependencies/blob/main/Fonts/allfonts.yml) manifest:

```yaml
Name: allfonts
Description: All Microsoft and Adobe essential fonts
Provider: Various
License: Mostly Microsoft EULA
License_url: https://www.microsoft.com/web/webpi/eula/net_library_eula_enu.htm
Dependencies: []

Steps:
- action: cab_extract
  file_name: arial32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/arial32.exe
  file_checksum: 9637DF0E91703179F0723EC095A36CB5
  
- action: cab_extract
  file_name: arialb32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/arialb32.exe
  file_checksum: C9089AE0C3B3D0D8C4B0A95979BB9FF0
  
- action: cab_extract
  file_name: andale32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/andale32.exe
  file_checksum: CBDC2FDD7D2ED0832795E86A8B9EE19A
  
- action: cab_extract
  file_name: comic32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/comic32.exe
  file_checksum: 2B30DE40BB5E803A0452C7715FC835D1
  
- action: cab_extract
  file_name: courie32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/courie32.exe
  file_checksum: 4E412C772294403AB62FB2D247D85C60
  
- action: cab_extract
  file_name: georgi32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/georgi32.exe
  file_checksum: 4D90016026E2DA447593B41A8D8FA8BD
  
- action: cab_extract
  file_name: impact32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/impact32.exe
  file_checksum: 7907C7DD6684E9BADE91CFF82683D9D7
  
- action: cab_extract
  file_name: times32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/times32.exe
  file_checksum: ED39C8EF91B9FB80F76F702568291BD5
  
- action: cab_extract
  file_name: trebuc32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/trebuc32.exe
  file_checksum: 0D7EA16CAC6261F8513A061FBFCDB2B5
  
- action: cab_extract
  file_name: verdan32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/verdan32.exe
  file_checksum: 12D2A75F8156E10607BE1EAA8E8EF120
  
- action: cab_extract
  file_name: webdin32.exe
  url: https://mirrors.kernel.org/gentoo/distfiles/webdin32.exe
  file_checksum: 230A1D13A365B22815F502EB24D9149B
  
- action: install_cab_fonts
  url: temp/arial32
  fonts: 
   - Ariali.TTF
   - Arialbd.TTF
   - Arialbi.TTF
   - Arial.TTF
  
- action: install_cab_fonts
  url: temp/arialb32
  fonts: 
   - AriBlk.TTF
  
- action: install_cab_fonts
  url: temp/arial32
  fonts: 
   - Ariali.TTF
   - Arialbd.TTF
   - Arialbi.TTF
   - Arial.TTF
  
- action: install_cab_fonts
  url: temp/andale32
  fonts: 
   - AndaleMo.TTF
  
- action: install_cab_fonts
  url: temp/comic32
  fonts: 
   - Comicbd.TTF
   - Comic.TTF
  
- action: install_cab_fonts
  url: temp/courie32
  fonts: 
   - cour.ttf
   - courbd.ttf
   - courbi.ttf
   - couri.ttf
  
- action: install_cab_fonts
  url: temp/georgi32
  fonts: 
   - Georgiaz.TTF
   - Georgiab.TTF
   - Georgiai.TTF
   - Georgia.TTF
  
- action: install_cab_fonts
  url: temp/arial32
  fonts: 
   - Ariali.TTF
   - Arialbd.TTF
   - Arialbi.TTF
   - Arial.TTF
  
- action: install_cab_fonts
  url: temp/impact32
  fonts: 
   - Impact.TTF
  
- action: install_cab_fonts
  url: temp/times32
  fonts: 
   - Times.TTF
   - Timesbd.TTF
   - Timesbi.TTF
   - Timesi.TTF
  
- action: install_cab_fonts
  url: temp/trebuc32
  fonts: 
   - trebuc.ttf
   - Trebucbd.ttf
   - trebucbi.ttf
   - trebucit.ttf
  
- action: install_cab_fonts
  url: temp/verdan32
  fonts: 
   - Verdanab.TTF
   - Verdanai.TTF
   - Verdanaz.TTF
   - Verdana.TTF
  
- action: install_cab_fonts
  url: temp/webdin32
  fonts: 
   - Webdings.TTF
```

Each manifest has a bunch of mandatory data:

* Name
* Description
* Provider
* License and License\_url
* Dependencies (not implemented so leave it blank)
* Steps

The **Name** should reflect the manifest file name (e.g. allfonts for allfonts.yml).

The **Description** is the full name of the dependency (e.g. All Microsoft and Adobe essential fonts)

The **Provider** is the owner of the source where the dependency files are located. This can also be the name of the creator of the software (e.g. Microsoft).

**License** and **License\_url** should be filled with the license name and url of the dependency we are going to install, normally these are offered with the software itself (e.g. Microsoft EULA, in case of multiple licenses, only the main license can be specified: Mostly Microsoft EULA).

The **Steps** are the instructions to follow to install the dependency. Bottles takes into account the order in which these are written and executes them in the same order.

### Propose new dependencies

There are two ways of proposing new dependencies:

* Filling a [new issue](https://github.com/bottlesdevs/dependencies/issues/new?assignees=mirkobrombin\&labels=request+dependency\&template=dependency-implementation-request.md\&title=%5BRequest+dependency%5D) following the template for the dependencies implementation request
* Implementing by yourself [Read more](https://github.com/bottlesdevs/dependencies#how-to-contribute)
