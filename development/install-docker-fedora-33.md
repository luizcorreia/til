## Install Docker on Fedora 33

With the release of Fedora 33, Docker is not supported by Fedora 33 officially.

This article will help you install Docker on Fedora 33.

### Remove old version
``` bash
sudo dnf remove docker-*
sudo dnf config-manager --disable docker-*
```

### Enable old CGroups

Docker still not support CgroupsV2.
``` bash
sudo grubby --update-kernel=ALL --args="systemd.unified_cgroup_hierarchy=0"
```

### Set up firewall

``` bash
sudo firewall-cmd --permanent --zone=trusted --add-interface=docker0
sudo firewall-cmd --permanent --zone=FedoraWorkstation --add-masquerade
```

### Install Moby

Moby is the open-source version of Docker.

``` bash
sudo dnf install moby-engine docker-compose
sudo systemctl enable docker
```
restart `sudo reboot`

### Test
``` bash
sudo docker run hello-world
```

Runing without sudo
``` bash
sudo groupadd docker
sudo usermod -aG docker $USER
```
//reboot to take effect
`sudo reboot`