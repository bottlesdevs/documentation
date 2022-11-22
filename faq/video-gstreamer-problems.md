# In-game videos problems

Wine uses GStreamer to play videos in games. There's a lot of codecs available for developers to encode their videos, and GStreamer needs different plugins for each of those codecs.

## Wine versions with bundled GStreamer plugins

Some Wine versions ships their own GStreamer plugins (like Wine-GE, Proton-GE). Bottles will try to use those embedded plugins if they are available by default.

Sometimes, this may cause problems, for example when embedded GStreamer plugins are outdated against your codecs on your system (for example on Arch Linux).

The best way to fix this, is to install on your system all GStreamer plugins (`gst-plugins-base`, `gst-plugins-good`, `gst-plugins-ugly`, `gst-plugins-bad`, and possibly more), and make the environnment variable `BOTTLES_USE_SYSTEM_GSTREAMER=1` available from the bottle or program. Multiple ways exists:

- Run Bottles with the variable: `BOTTLES_USE_SYSTEM_GSTREAMER=1 bottles`
- Add the environment variable to the bottle
- Add the environment variable to the program using launch parameters

## Wine versions without GStreamer plugins

Classic Wine, Caffe, Soda, Vaniglia and most of the Wine versions do not ship any GStreamer plugins. This may cause problems when launching games, as if a GStreamer installation is not found on your system, videos won't play.

Here's an example of a GStreamer plugin missing:
```
winegstreamer error: decodebin0: Your GStreamer installation is missing a plug-in.
winegstreamer error: decodebin0: ../gst/playback/gstdecodebin2.c(4701): gst_decode_bin_expose (): /GstBin:bin0/GstDecodeBin:decodebin0:
no suitable plugins found:
Missing decoder: Advanced Streaming Format (ASF) (video/x-ms-asf)
```

You should install GStreamer, and all plugins that are published by GStreamer. You should look at your distro wiki page about it, but plugins are usually named `gst-plugins-base`, `gst-plugins-good`, `gst-plugins-ugly`, `gst-plugins-bad`.