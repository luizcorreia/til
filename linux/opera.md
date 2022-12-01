## Opera Linux browser - h.264 support (through x264 open source codec) 

Opera will automatically use the version in lib_extra and the mod will survive opera upgrades. So you'll only need to do this once.

```sh
#!/bin/bash
# Dependency: curl unzip
curl -L -O https://github.com/nwjs-ffmpeg-prebuilt/nwjs-ffmpeg-prebuilt/releases/download/0.70.1/0.70.1-linux-x64.zip
unzip 0.64.0-linux-x64.zip
sudo mkdir /usr/lib64/opera/lib_extra
sudo mv libffmpeg.so /usr/lib/x86_64-linux-gnu/opera/lib_extra
```

> Tested on Fedora 35
