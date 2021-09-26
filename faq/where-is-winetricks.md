# Where is Winetricks?

In v2 we have chosen to adopt our dependency system instead of the usual Winetricks.

### What are dependencies?

Dependencies on Bottles are like package dependencies on almost all Linux distributions. Software may require dependencies in order to run and these can be downloaded and installed manually or via our dependency manager who will take care of everything \(because each dependency can depend on other dependencies\).

Read more about, [here](https://docs.usebottles.com/bottles/dependencies).

### Why not Winetricks?

We want to offer a centralized dependency management system. We want to be able to trace those installed in the bottle configuration file to be able to remove them or simply share the bottle with all dependencies listed.

Also, with an internal system it will be easier to install dependencies when an Environment is chosen.For example the Software environment requires vcrun, corefonts and several others. With our system we can install the dependencies at the bottle creation, without exiting the software or using external ones.

**Extensibility**. Using external repositories for dependencies and providing these with a manifest containing instructions and dependencies, it will be easier to add new dependencies to Bottles and extend support for new software.

Finally, Winetricks is external software and clashes with our UI 😏.

### A community driven repository

Our [repository](https://github.com/bottlesdevs/dependencies) will be community driven. This mean that other users can open Pull Requests to provide new dependency support to Bottles!

Online database: [https://usebottles.com/database/dependencies](https://usebottles.com/database/dependencies)

