# My fork of dwm - Suckless' Dynamic Windows Manager

## Original README

```
dwm - dynamic window manager
============================
dwm is an extremely fast, small, and dynamic window manager for X.

Requirements
------------
In order to build dwm you need the Xlib header files.

Installation
------------
Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

Afterwards enter the following command to build and install dwm (if
necessary as root):

    make clean install

Running dwm
-----------
Add the following line to your .xinitrc to start dwm using startx:

    exec dwm

In order to connect dwm to a specific display, make sure that
the DISPLAY environment variable is set correctly, e.g.:

    DISPLAY=foo.bar:1 exec dwm

(This will start dwm on display :1 of the host foo.bar.)

In order to display status info in the bar, you can do something
like this in your .xinitrc:

    while xsetroot -name "`date` `uptime | sed 's/.*,//'`"
    do
    	sleep 1
    done &
    exec dwm

Configuration
-------------
The configuration of dwm is done by creating a custom config.h
and (re)compiling the source code.
```

## Changes to the original project

- Added keyboard shortcuts
- Addition of a `dwm-startup` shell script, handling the startup process, statusbar and battery managment (for laptops)
- Different colorscheme
- Patches applied: [tilegap](https://dwm.suckless.org/patches/tilegap/)

## Installation

The installation is done simply by running:

```sh
make install_add        # The dwm-startup install
sudo make clean install # The base DWM installation
```

Afterwards, make sure you satisfy the dependencies.

## Keymaps

`dwm`'s default keymaps are nicely presented in [erlendaakre's cheatsheet](https://gist.github.com/erlendaakre/12eb90eef84a3ab81f7b531e516c9594).

Here are the new additions:

| Mask             | Key    | Function                                            |
| -                | -      | -                                                   |
| ModKey-ShiftMask | M      | Spawn an instance of `alsamixer`                    |
| ModKey-ShiftMask | S      | Spawn an instance of `screencap`                    |
| ModKey-ShiftMask | X      | Spawn an instance of `slock`                        |
| ModKey-ShiftMask | W      | Spawn an instance of `mpv` focusing `/dev/video0`   |

## Dependencies

| Tool name   | Tool provider                                              | Reason for use                |
| -           | -                                                          | -                             |
| `acpi`      | `acpi`                                                     | Statusbar (battery)           |
| `dmenu`     | `dmenu`                                                    | Selection making              |
| `feh`       | `feh`                                                      | Background image display      |
| `iwgetid`   | `wireless_tools`                                           | Statusbar (connection)        |
| `mpv`       | `mpv`                                                      | Shortcut (Webcam)             |
| `nmcli`     | `networkmanager`                                           | Statusbar (connection)        |
| `screencap` | [`bash-scripts`](https://github.com/bratpeki/bash-scripts) | Shortcut (Screen capture)     |
| `slock`     | `slock`                                                    | Shortcut (Screen locking)     |
| `xcompmgr`  | `xcompmgr`                                                 | Transparency (`st` terminals) |
