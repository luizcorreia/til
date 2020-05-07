## Solution to the HiDPI problem from Davinci Resolve on Linux


For easy launching in HiDPI make these changes to the desktop shortcut, for example with nano editor:

```sh
  sudo nano /usr/share/applications/com.blackmagicdesign.resolve.desktop
```

change the Exec line value:

```sh 
  Exec=env QT_DEVICE_PIXEL_RATIO=2 /opt/resolve/bin/resolve %U
```
