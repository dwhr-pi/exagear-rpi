# WinwHQ 
https://wiki.winehq.org/Debian



# exagear-rpi
installing Exagear Desktop on the newer Raspberry Pies

thanks to [this guide](https://insrt.uk/post/exagear-install).

Exagear Desktop is a discontinued piece of software that could be used to emulate x86 applications on ARM devices.

### Installation Steps
First install prerequisites with `apt`
```
sudo apt-get update
sudo apt-get install -y bash coreutils findutils curl binfmt-support cron
```

Create a new directory (to download the packages and key)
```
mkdir ~/exagear
cd ~/exagear
```

Download and install required Exagear packages (follow the instructions for your bitness)
```
# 32-bit
wget https://archive.org/download/exagear-desktop_202111/exagear_3428-1_armhf.deb
wget https://archive.org/download/exagear-desktop_202111/exagear-dsound-server_010_armhf.deb
wget https://archive.org/download/exagear-desktop_202111/exagear-guest-debian-9_3428_all.deb
sudo dpkg -i exagear_3428-1_armhf.deb
sudo dpkg -i exagear-dsound-server_010_armhf.deb
sudo dpkg -i exagear-guest-debian-9_3428_all.deb

# 64-bit
wget https://archive.org/download/exagear-desktop_202111/exagear_3428-1_arm64.deb
wget https://archive.org/download/exagear-desktop_202111/exagear-dsound-server_010_arm64.deb
wget https://archive.org/download/exagear-desktop_202111/exagear-guest-debian-9_3428_all.deb
sudo dpkg -i exagear_3428-1_arm64.deb
sudo dpkg -i exagear-dsound-server_010_arm64.deb
sudo dpkg -i exagear-guest-debian-9_3428_all.deb
```

Patch exagear license
```
curl https://archive.org/download/exagear-desktop_202111/patch.sh | sudo bash
```

Now, run `exagear`, and you're in an x86 environment! Make sure to run the following to update the subsystem:
```
sudo apt-get update && sudo apt-get upgrade -y
```

There was an error, key is obsoled.
`curl https://dl.insrt.uk/mirror/exagear/patch.sh | sudo bash` will fix it.

Next read: https://www.raspberry-pi-geek.de/ausgaben/rpg/2018/10/x86-programme-auf-dem-raspi-ausfuehren/  
And other at: https://www.ephesossoftware.com/articles/linux/how-to-install-windows-software-on-raspberry-pi-using-wine.html  
https://www.youtube.com/watch?v=g7hFeaAl-oI

