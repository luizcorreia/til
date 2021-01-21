## Change the default language from a app on .desktop file

I would like to start the virt-manager with a language (English) other than my locale one (Portuguese).

This is my virt-manager.desktop:

```s
[Desktop Entry]
Name=Virtual Machine Manager
Icon=virt-manager
Exec=/bin/bash -c "LANGUAGE=en_US virt-manager"
Type=Application
Terminal=false
Categories=System;
```
Just change Exec to `Exec=/bin/bash -c "LANGUAGE=en_US virt-manager"`

### Note

Make sure you run the application from the local .desktop file: After editing the local one, make sure you log out / in before running it again.

A more generic way, compared to playing with a .desktop file is to create the file $HOME/.local/bin/virt-manager and give it this contents:

```bash
#!/bin/sh
export LANGUAGE=en_US
exec /usr/bin/virt-manager $@
```

Also run chmod +x $HOME/.local/bin/virt-manager. Then, next time you log in, English will be the display language however you start virt-manager.