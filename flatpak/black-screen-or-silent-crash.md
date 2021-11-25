---
description: Is your executable showing a black screen or is it silently crashing?
---

# Black screen or silent crash

Some programs may fail to start or show a black screen when unable to access files. This is due to the Flatpak sandbox, as the executable was started from outside the sandbox and the runner is unable to access some necessary files. Nonetheless, it's easy to fix without having to disable the sandbox.



### How to fix

To fix the problem, just place the files inside the sandbox, an easy process that takes a few seconds. Access the bottle screen where we want to launch the executable and press on **Browse C:**

![Press on Browse C: in the bottle view](<../.gitbook/assets/image (42).png>)

this will popup the system file manager to the bottle C: drive path, then paste your files here (normally these problems doesn't came with standalone executable, therefore you should have a folder with multiple files, for example as a result of an extraction, then copy the entire folder, not the single executable).

![](<../.gitbook/assets/image (43).png>)

After placing the files, go back to Bottles and access the Programs section from the sidebar and **Add a new program**: by clicking the **+** in the headerbar, here browse to the folder and pick the executable. Next time start it from the Programs section and it should start finding all the needed files.

