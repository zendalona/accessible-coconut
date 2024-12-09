**Accessible-Coconut** is a community-driven GNU/Linux operating system that is fully accessible for individuals with visual impairments. AC is based on Ubuntu MATE. The goal is to create a free and open-source desktop environment that is accessible without relying on vision.

**Version Accessible-Coconut-24.04.01**
Note : This version of GNU/Linux distribution is not for sale. However charges for installation, maintenance and training is deserving.


For more information visit : https://zendalona.com/accessible-coconut/

Download link: https://sourceforge.net/projects/accessible-coconut/

Download Statistics : https://sourceforge.net/projects/accessible-coconut/files/stats/map

Forum : https://groups.google.com/forum/#!forum/accessible-coconut

Telegram forum : https://telegram.me/accessible_coconut

**Install cubic from PPA** 
```
sudo apt-add-repository universe 

sudo apt-add-repository ppa:cubic-wizard/release 

sudo apt update 

sudo apt install --no-install-recommends cubic

```
Remaster Routines 

1. Update version and date in cubic interface 

2. Update remaster log and version in /usr/share/Coconut/customization_details.text 

3. apt-get clean from chroot 

4. Remove orphanes using apt-get purge $(deborphan) 

5. Update coco-patcher 

6. Update boot/grub/grub.cfg 

  

Warning: Add amd64 with filename  

Warning: Do not use hyphen (-) in "Volume Id" field 

Warning: Always fill Release Name Completely like "Accessible-Coconut 24.04 LTS "Noble Numbat" - Release amd64 (20180903)" 

  

List of packages that requires care while updating  


| Package   | Reasons |
| --------- | ------- |
| firefox*  |     a11y    |
| libreoffice* |       a11y  |
| gnome-session-canberra    |     login sound patch    |
| chromium   |     a11y&launcher customization    |
| plymouth-theme-ubuntu-mate-text|  customization    |
| plymouth-theme-ubuntu-mate-logo|  customization   |
| plymouth plymouth-label| customization        |
|plymouth theme-spinner | customization |
|plymouth-theme-ubuntu-text|customization|
|yaru-theme-icon|installer-icon & main menu icon|

***Steps Done In each customization of Accessible-Coconut***

System Update
```
apt update
apt upgrade

```

Install Application from Repository
```
apt-get install synaptic gdebi acpi artha audacious audacity festival gnuchess phalanx gparted lame mpg321 p7zip smplayer vlc pidgin gelemental xbacklight git-core brasero fairymax speech-dispatcher-festival speech-dispatcher-flite rhvoice speech-dispatcher-rhvoice pandoc libttspico-utils vco-plugins tap-plugins swh-plugins rev-plugins omins mcp-plugins links2 handbrake net-tools usb-creator-gtk lmms kdeconnect ssh xserver-xorg-input-synaptics preload gimp daisy-player ebook-speaker cpu-x uget
````
