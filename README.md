Antx's build of dwm
============================
dwm is an extremely fast, small, and dynamic window manager for X.

BTW, my scripts are in [this repository](https://github.com/antx-code/scripts).

Requirements
------------
In order to build dwm you need the Xlib header files.

Installation
------------
If you are in Manjaro or any arch linux envirement, you should install dwm first with yay, which like below:

    yay -S dwm

Edit config.mk to match your local setup (dwm is installed into
the /usr/local namespace by default).

If you want to use my dwm fonts, you can download nerd-fonts with yay like below:

    yay -S nerd-fonts-source-code-pro

or

    yay -S nerd-fonts-complete

Afterwards enter the following command to build and install dwm (if
necessary as root):

    sudo make clean install

Patches applied
---------------
- [dwm-alpha-20180613-b69c870.diff](https://dwm.suckless.org/patches/alpha/)
- [dwm-autostart-20161205-bb3bd6f.diff](https://dwm.suckless.org/patches/autostart/)
- [dwm-awesomebar-20191003-80e2a76.diff](https://dwm.suckless.org/patches/awesomebar/)
- [dwm-fullscreen-6.2.diff](https://dwm.suckless.org/patches/fullscreen/)
- [dwm-hide-and-restore.diff](https://github.com/theniceboy/dwm-hide-and-restore-win.diff) (a custom patch by @theniceboy)
- [dwm-hide_vacant_tags-6.2.diff](https://dwm.suckless.org/patches/hide_vacant_tags/)
- [dwm-noborder-6.2.diff](https://dwm.suckless.org/patches/noborder/)
- [dwm-pertag-20170513-ceac8c9.diff](https://dwm.suckless.org/patches/pertag/)
- [dwm-r1522-viewontag.diff](https://dwm.suckless.org/patches/viewontag/)
- [dwm-rotatestack-20161021-ab9571b.diff](https://dwm.suckless.org/patches/rotatestack/)
- [dwm-vanitygaps-20190508-6.2.diff](https://dwm.suckless.org/patches/vanitygaps/)

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
