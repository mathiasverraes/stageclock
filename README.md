# Stageclock

Just open `index.html` in a browser.

## Raspberry Pi / Raspbian Boot in Chromium Kiosk mode

Edit `/etc/xdg/lxsession/LXDE/autostart` to turn off screensaver

```
#@xscreensaver -no-splash
@xset s off
@xset -dpms
@xset s noblank
```

Add a bash script in `/home/pi/Desktop/clock` to launch it in chromium kiosk mode:

```
#!/usr/bin/env bash
chromium-browser --kiosk --app=file:///home/pi/stageclock/index.html
```

Don't forget to `chmod +x /home/pi/Desktop/clock`

Edit `/home/pi/.config/lxsession/LXDE-pi/autostart` to load it automatically on boot:

```
@/home/pi/Desktop/clock
```
