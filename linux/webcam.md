# Logitech c920 configuration via v4l2-ctl

Bad autofocus
The autofocus on this webcam is horrible! I did myself a favor and promptly turned it off. With the v4l-utils package installed, do this (assuming your Logitech C920 is /dev/video0):

```sh
v4l2-ctl -d /dev/video0 --set-ctrl=focus_auto=0
v4l2-ctl -d /dev/video0 --set-ctrl=focus_absolute=0
```

## Other settings

To see the other settings that are available for the Logitech C920 webcam:

```sh
v4l2-ctl -d /dev/video0 --list-ctrls-menus
```

You can manually tune the brightness, contrast, saturation, white balance temperature, sharpness, exposure and gain settings with v4l2-ctl.

## My actual configuration

```sh
#!/usr/bin/env bash
v4l2-ctl -d /dev/video0 --set-ctrl=sharpness=140
v4l2-ctl -d /dev/video0 --set-ctrl=focus_automatic_continuous=0
v4l2-ctl -d /dev/video0 --set-ctrl=focus_absolute=10
v4l2-ctl -d /dev/video0 --set-ctrl=power_line_frequency=1
v4l2-ctl -d /dev/video0 --set-ctrl=auto_exposure=1
v4l2-ctl -d /dev/video0 --set-ctrl=exposure_time_absolute=500
v4l2-ctl -d /dev/video0 --set-ctrl=contrast=130
v4l2-ctl -d /dev/video0 --set-ctrl=saturation=120
v4l2-ctl -d /dev/video0 --set-ctrl=white_balance_automatic=0
v4l2-ctl -d /dev/video0 --set-ctrl=white_balance_temperature=4000
v4l2-ctl -d /dev/video0 --set-ctrl=gain=50
v4l2-ctl -d /dev/video0 --set-ctrl=zoom_absolute=140

```
