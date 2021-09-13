# NVIDIA GeForce NOW on Linux

A launcher for NVIDIA GeForce NOW on Linux.

Please there's no longer a need for hacks to run GeForce NOW on Linux since NVIDIA enabled access to the service via Chrome.
\
As a consequence this script no longer spoofs the browser user agent by default anymore (i.e. it no longer pretends to run under ChromeOS unless explicitly told to). However the original behaviour can be enabled by setting the corresponding variable.
\
It's still somewhat useful since it launches in app mode, feeling more like the native app on other OSes. 

### Original motivation

Previously GeForce NOW didn't offer support for Linux but did support Chrome OS through the browser. As commented on [this article](https://www.gamingonlinux.com/2020/08/nvidia-geforce-now-adds-chromebook-support-so-you-can-run-it-on-linux-too), since Chrome OS is based on Linux this meant it could be exploited to run on Linux.

This script originally launched a chrome browser window with the user agent string modified to *look* like it was running on Chrome OS.

## Options and default behaviour

The script behaviour can be modified by setting the appropriate environment variables (or by modifying the script directly).

These are the configurable options:

- `START_MAXIMIZED`: Default: **On**. Starts maximized but not completely full screen.
- `START_IN_INCOGNITO`: Default: **Off**. Starts in incognito mode (note this doesn't appear to work at least on my system).
- `START_FULLSCREEN`: Default: **On**. Starts full screen (no titlebar), exit fullscreen with F11, close with Alt+F4.
- `OVERRIDE_USER_AGENT`: Default: **Off**. Pretend to be running under ChromeOS via the User Agent string.
- `CHROMIUM_VARIANTS`: List on browsers to try, in order or preference (see [*Supported browsers*](#supported_browsers)). \
    Default: google-chrome, microsoft-edge, vivaldi, microsoft-edge-dev, chromium 

To invoke e.g. neither maximized nor fullscreen:
```shell
$ START_MAXIMIZED=0 START_FULLSCREEN=0 geforce-now-linux
```

GeForce NOW is launched in *app mode* (i.e. the bowser address bar, tabs and menus aren't shown).

## Supported browsers <a name="supported_browsers"></a>

The script will try to run on the first *Chromium variant* found on the system, so far I've only tested it on Chromium (where it errors upon starting a game) and Google Chrome (where it works). Probably Google Chrome is the safest bet.

Note Opera doesn't appear to support *app mode*, so it isn't included in the list.
