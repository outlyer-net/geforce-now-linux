# NVIDIA GeForce NOW on Linux

A launcher for NVIDIA GeForce NOW on Linux.

GeForce NOW doesn't offer support for Linux but it does offer support for Chrome OS through the browser. As commented on [this article](https://www.gamingonlinux.com/2020/08/nvidia-geforce-now-adds-chromebook-support-so-you-can-run-it-on-linux-too), since Chrome OS is based on Linux this means it can be exploited to run on Linux.

This script launches a chrome browser window with the user agent string modified to *look* like it's running on Chrome OS.

**DISCLAIMER**: Use at your own risk, NVIDIA might decide to prevent Linux users from accessing the service or start relying on some Chrome OS-specific feature that breaks this script. Don't subscribe to GeForce NOW solely based on the fact this method exists!

## Options and default behaviour

The script behaviour can be changed by modifying some of the variables set in it. Those are clearly labeled in the script.

By default it will run full screen (i.e. the same as pressing F11 on most browsers). The *close window* button won't be shown either, exiting full screen (F11) will display it, while Alt+F4 will close the window on most systems.

GeForce NOW is launched in *app mode* (i.e. the bowser address bar, tabs and menus aren't shown).

## Supported browsers

The script will try to run on the first *Chromium variant* found on the system, so far I've only tested it on Chromium (where it errors upon starting a game) and Google Chrome (where it works). Probably Google Chrome is the safest bet.
