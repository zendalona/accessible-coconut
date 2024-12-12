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
**telegram-purple,Avidemux excluded, check whether CPU-X is already there  in the latest mate 

<h4> Copying Coconut Files </h4>

Copy directory “Coconut” from old version and paste it into new version in the same path 

 Path:      /usr/share/Coconut 


Also Copy “applications” old version and paste it in the same path in new version 

 Path:      /usr/local/share/applications 

Now update launcher database update 
 
```
update-desktop-database
```

Updating Schemas 

We need to edit the “/usr/share/glib-2.0/schemas/org.mate.marco.gschema.xml” 

  nano /usr/share/glib-2.0/schemas/org.mate.marco.gschema.xml 

 Now copy the below code and paste it after Command-12. 
 
 Below command-12 
 ```
<key name="command-13" type="s"> 

<default>' '</default> 

<summary>Commands to run in response to keybindings</summary> 

<description>The /apps/marco/global_keybindings/run_command_N 

keys define keybindings that correspond to these commands. 

Pressing the keybinding for run_command_N will execute command_N.</description> 

</key> 

<key name="command-14" type="s"> 

<default>' '</default> 

<summary>Commands to run in response to keybindings</summary> 

<description>The /apps/marco/global_keybindings/run_command_N keys 

define keybindings that correspond to these commands. Pressing the 

keybinding for run_command_N will execute command_N.</description> 

</key> 

<key name="command-15" type="s"> 

<default>' '</default> 

<summary>Commands to run in response to keybindings</summary> 

<description>The /apps/marco/global_keybindings/run_command_N keys define 

keybindings that correspond to these commands. Pressing the keybinding 

for run_command_N will execute command_N.</description> 

</key>
```
Now add the below code under run-command-12 in the same file:
```
<key name="run-command-13" type="s"> 

<default>'disabled'</default> 

<summary>Run a defined command</summary> 

<description>The keybinding that runs the correspondingly-numbered command 

in /apps/marco/keybinding_commands The format looks like "&lt;Control&gt;a" 

or "&lt;Shift&gt;&lt;Alt&gt;F1". The parser is fairly liberal and allows 

lower or upper case, and also abbreviations such as "&lt;Ctl&gt;" and 

"&lt;Ctrl&gt;". If you set the option to the special string "disabled", 

then there will be no keybinding for this action.</description> 

</key> 

<key name="run-command-14" type="s"> 

<default>'disabled'</default> 

<summary>Run a defined command</summary> 

<description>The keybinding that runs the correspondingly-numbered command 

in /apps/marco/keybinding_commands The format looks like "&lt;Control&gt;a" 

or "&lt;Shift&gt;&lt;Alt&gt;F1". The parser is fairly liberal and allows lower 

or upper case, and also abbreviations such as "&lt;Ctl&gt;" and "&lt;Ctrl&gt;". 

If you set the option to the special string "disabled", then there will be no 

keybinding for this action.</description> 

</key> 

<key name="run-command-15" type="s"> 

<default>'disabled'</default> 

<summary>Run a defined command</summary> 

<description>The keybinding that runs the correspondingly-numbered 

command in /apps/marco/keybinding_commands The format looks like 

"&lt;Control&gt;a" or "&lt;Shift&gt;&lt;Alt&gt;F1". The parser is 

fairly liberal and allows lower or upper case, and also abbreviations 

such as "&lt;Ctl&gt;" and "&lt;Ctrl&gt;". If you set the option to the 

special string "disabled", then there will be no keybinding for this 

action.</description> 

</key>
```
Ambiant-MATE theme installed 
```
add-apt-repository ppa:lah7/ambiant-mate 

apt-get install ambiant-mate-gtk-themes
```
Now copy z-mate.gschema.override from /usr/share/glib-2.0/schemas to your /usr/share/glib-2.0/schemas/ 

then compile-schemas by 
```
glib-compile-schemas /usr/share/glib-2.0/schemas 
```
Default Menu bar items and their positions defined 

 Open “familiar.layout” from the following path 

   Path: /usr/share/mate-panel/layouts/familiar.layout 

 Edit this file using nano command: 
```
   nano /usr/share/mate-panel/layouts/familiar.layout 
```
  What to edit: 

    Add the following:  
```
   [Object menu-bar] 

object-type=menu-bar 

toplevel-id=top 

position=0 

locked=true 
```
    

 Edit [briskmenu] entry with following: 
```
[Object briskmenu] 

object-type=applet 

applet-iid=BriskMenuFactory::BriskMenu 

toplevel-id=bottom 

position=0 

locked=true 
```
  

Edit [show-desktop] 
```
[Object show-desktop] 

Position = 15 
```
Add following line to show-desktop 
```
panel-right-stick=true 
```
Panel Application customized Menu 

XDG Mate customized Menu 

Edit the following file with the below entries: 
```
nano /etc/xdg/menus/mate-applications.menu 
```
Logout, Shutdown and Seperator (add this at the end of <-- End Other -->and <Menu><-- End Applications -->) 
The background color is `#ffffff` for light mode and `#000000` for dark mode.
