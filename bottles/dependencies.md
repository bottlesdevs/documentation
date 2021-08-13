---
description: >-
  You can manage dependencies for Windows programs in a few simple clicks thanks
  to our built-in dependency manager.
---

# Dependencies

Here you can extend your bottle compatibility adding new dependencies. These are Windows software and libraries installed by Bottles trough automation.

Some dependencies examples are:

* vcredist \(2013, 2015, 2019\)
* dotnet \(3.5, 3.5 sp1, 4.0, 4.7.2, 4.8\)
* dotnetcore3
* msxml \(3, 6\)
* d3dx9,
* d3compiler \(43, 46, 47\)
* ffdshow
* dirac

and others, see [here](https://usebottles.com/database/dependencies/) more.

This is one of our most important features in Bottles. It is based on a public and community driven [repository](https://github.com/bottlesdevs/dependencies) where maintainers can propose new dependencies. [Read more](../contribute/missing-dependencies.md).

If your bottle has the experimental [versioning](versioning.md) feature enabled, a new [state](versioning.md#how-versioning-works) will be generated after the dependency installation.

Dependencies can also automatically be installed by the official Bottles installers. So if you choose to install e.g. the epicgamestore installer, you will see the new dependencies installed after the process.



