# NVIDIA GeForce NOW on Linux

A launcher for NVIDIA GeForce NOW on Linux.

GeForce NOW doesn't offer support for Linux but it does offer support for Chrome OS through the browser. As commented on [this article](https://www.gamingonlinux.com/2020/08/nvidia-geforce-now-adds-chromebook-support-so-you-can-run-it-on-linux-too), since Chrome OS is based on Linux this means it can be exploited to run on Linux.

This script launches a chrome browser window with the user agent string modified to *look* like it's running on Chrome OS.

**DISCLAIMER**: Use at your own risk, NVIDIA might decide to prevent Linux users from accessing the service or start relying on some Chrome OS-specific feature that breaks this script. Don't subscribe to GeForce NOW solely based on the fact this method exists!

## Options and default behaviour

The script behaviour can be modified by setting the appropriate environment variables (or by modifying the script directly).

These are the configurable options:

- `START_MAXIMIZED`: Default: **On**. Starts maximized but not completely full screen.
- `START_IN_INCOGNITO`: Default: **Off**. Starts in incognito mode (note this doesn't appear to work at least on my system).
- `START_FULLSCREEN`: Default: **On**. Starts full screen (no titlebar), exit fullscreen with F11, close with Alt+F4.
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
