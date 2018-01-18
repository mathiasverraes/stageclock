# stageclock


## Raspberry Pi / Raspbian

Edit `/etc/xdg/lxsession/LXDE/autostart` to turn off screensaver

```
#@xscreensaver -no-splash
@xset s off
@xset -dpms
@xset s noblank
```

Add a bash script to launch it in chromium kiosk mode

```
#!/usr/bin/env bash
chromium-browser --kiosk --app=file:///home/pi/stageclock/index.html
```
