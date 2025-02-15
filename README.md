# WinwHQ 
https://wiki.winehq.org/Debian

```
sudo dpkg --add-architecture i386 
```

```
sudo mkdir -pm755 /etc/apt/keyrings
sudo wget -O /etc/apt/keyrings/winehq-archive.key https://dl.winehq.org/wine-builds/winehq.key
```

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


https://www.instructables.com/How-to-Set-Up-Wine-on-Raspberry-Pi-1/
Open a new terminal and typ `exagear`
Then type in `arch`

Open a new terminal and typ `sudo apt-get install wine`

https://thepigamer.blogspot.com/2021/01/performance-topic-running-x86-games-on.html

`sudo apt-get install wine32`

https://www.ephesossoftware.com/articles/linux/how-to-install-windows-software-on-raspberry-pi-using-wine.html
https://www.instructables.com/How-to-Set-Up-Wine-on-Raspberry-Pi-1/

https://www.magpi.de/news/box86-wine-windows-programme-auf-dem-raspberry-pi








## Steam installation in der i868 Umgebung.
exagear
arch

apt --fix-broken install

Installiert die notwendigen Depencies in die i868 Umgebung nach, die nicht aus der arch64 Umgebung dem i868 zur Verfügung stehen. 
Installiert somit in gewisser Weise ein i386 Linux nach... 

Sollte nichts passieren, einfach mal manuell diese nachfolgenden apt's installieren versuchen, spätestens dann sollte Linux den Fehler der fehlenden Systemdateien bemerken und zu dem zuvor genannten fix aufrufen. 

apt-get install apt-transport-https
apt-get install curl
apt-get install file
apt-get install libnss3
apt-get install policykit-1
apt-get install python3
apt-get install python3-apt
apt-get install xterm
apt-get install gnome-terminal
apt-get install konsole
apt-get install x-terminal-emulator
apt-get install xz-utils
apt-get install zenity
apt-get install 
apt-get install 

Das nachinstallieren der fehlenden Systemdateien dauert eine Weile.... 



Db hier geht es jedenfalls weiter: 
cd Downloads
dpkg -i steam_latest.deb

Normalerweise fertig.

sudo apt autoremove

it looks like wine32 is missing, you should install it.
as root, please execute "apt-get install wine32"






