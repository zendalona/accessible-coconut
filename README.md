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
<h3>Panel Application customized Menu</h3> 

XDG Mate customized Menu 

Edit the following file with the below entries: 
```
nano /etc/xdg/menus/mate-applications.menu 
```
Logout and Shutdown Seperator (add this at the end of <-- End Other -->and <Menu><-- End Applications -->) 
```
<Include> 

    <Filename>shutdown.desktop</Filename> 

    <Filename>logout.desktop</Filename> 

  </Include> 

  

  <!-- Separator between menus and shutdown --> 

  <Layout> 

    <Merge type="menus"/> 

    <Merge type="files"/> 

    <Separator/> 

    <Filename>logout.desktop</Filename> 

    <Filename>shutdown.desktop</Filename> 

    <Separator/> 

  </Layout> 
```
Add Terminal in Accessories (just add the first line only above end accessories) 
```
<Filename>mate-terminal.desktop</Filename> 

</Include> 

</Menu> <! -- End Accessories -->
```
Add Preference in System Tools 

(add below the first </Include> closing tag and in between the closing menu of </menu>    System tools <!-- End System Tools -->) 
```
<Menu> 

<Name>Preferences</Name> 

<Directory>Settings.directory</Directory> 

<Include> 

<And> 

<Category>Settings</Category> 

<Not> 

<Or> 

<Category>System</Category> 

<Category>X-GNOME-Settings-Panel</Category> 

<Filename>authconfig.desktop</Filename> 

<Filename>ca.desrt.dconf-editor.desktop</Filename> 

<Filename>fedora-release-notes.desktop</Filename> 

<Filename>firewall-config.desktop</Filename> 

<Filename>flash-player-properties.desktop</Filename> 

<Filename>gconf-editor.desktop</Filename> 

<Filename>gnome-abrt.desktop</Filename> 

<Filename>ibus-setup-anthy.desktop</Filename> 

<Filename>ibus-setup.desktop</Filename> 

<Filename>ibus-setup-hangul.desktop</Filename> 

<Filename>ibus-setup-libbopomofo.desktop</Filename> 

<Filename>ibus-setup-libpinyin.desktop</Filename> 

<Filename>ibus-setup-m17n.desktop</Filename> 

<Filename>ibus-setup-typing-booster.desktop</Filename> 

<Filename>im-chooser.desktop</Filename> 

<Filename>itweb-settings.desktop</Filename> 

<Filename>jhbuild.desktop</Filename> 

<Filename>javaws.desktop</Filename> 

<Filename>java-1.7.0-openjdk-jconsole.desktop</Filename> 

<Filename>java-1.7.0-openjdk-policytool.desktop</Filename> 

<Filename>log4j-chainsaw.desktop</Filename> 

<Filename>log4j-logfactor5.desktop</Filename> 

<Filename>nm-connection-editor.desktop</Filename> 

<Filename>org.gnome.PowerStats.desktop</Filename> 

<Filename>setroubleshoot.desktop</Filename> 

<Filename>system-config-date.desktop</Filename> 

<Filename>system-config-firewall.desktop</Filename> 

<Filename>system-config-keyboard.desktop</Filename> 

<Filename>system-config-language.desktop</Filename> 

<Filename>system-config-printer.desktop</Filename> 

<Filename>system-config-users.desktop</Filename> 

<Filename>vino-preferences.desktop</Filename> 

</Or> 

</Not> 

</And> 

</Include> 

</Menu> 

<Menu> 

<Name>Administration</Name> 

<Directory>Settings-System.directory</Directory> 

<Include> 

<And> 

<Category>Settings</Category> 

<Category>System</Category> 

<Not> 

<Or> 

<Category>X-GNOME-Settings-Panel</Category> 

<Filename>authconfig.desktop</Filename> 

<Filename>ca.desrt.dconf-editor.desktop</Filename> 

<Filename>fedora-release-notes.desktop</Filename> 

<Filename>firewall-config.desktop</Filename> 

<Filename>flash-player-properties.desktop</Filename> 

<Filename>gconf-editor.desktop</Filename> 

<Filename>gnome-abrt.desktop</Filename> 

<Filename>ibus-setup-anthy.desktop</Filename> 

<Filename>ibus-setup.desktop</Filename> 

<Filename>ibus-setup-hangul.desktop</Filename> 

<Filename>ibus-setup-libbopomofo.desktop</Filename> 

<Filename>ibus-setup-libpinyin.desktop</Filename> 

<Filename>ibus-setup-m17n.desktop</Filename> 

<Filename>ibus-setup-typing-booster.desktop</Filename> 

<Filename>im-chooser.desktop</Filename> 

<Filename>itweb-settings.desktop</Filename> 

<Filename>jhbuild.desktop</Filename> 

<Filename>javaws.desktop</Filename> 

<Filename>java-1.7.0-openjdk-jconsole.desktop</Filename> 

<Filename>java-1.7.0-openjdk-policytool.desktop</Filename> 

<Filename>log4j-chainsaw.desktop</Filename> 

<Filename>log4j-logfactor5.desktop</Filename> 

<Filename>nm-connection-editor.desktop</Filename> 

<Filename>org.gnome.PowerStats.desktop</Filename> 

<Filename>setroubleshoot.desktop</Filename> 

<Filename>system-config-date.desktop</Filename> 

<Filename>system-config-firewall.desktop</Filename> 

<Filename>system-config-keyboard.desktop</Filename> 

<Filename>system-config-language.desktop</Filename> 

<Filename>system-config-printer.desktop</Filename> 

<Filename>system-config-users.desktop</Filename> 

<Filename>vino-preferences.desktop</Filename> 

</Or> 

</Not> 

</And> 

</Include> 

</Menu>
```
<h3>Enabled Preferences and Administration in Mate System tools menu</h3> 

Copy from old Accessible Coconut 

/etc/xdg/menus/gnome-applications.menu 

Icons for main menu 

copy tree.svg (icon of AC) rename as start-here-symbolic.svg and replace in: 

/usr/share/icons/Yaru/scalable/places/start-here-symbolic.svg 

If still the icons are unchanged change all the start-here.png in /usr/share/icons/Yaru/8x8/16x16/ etc..... with start-here.png in Coconut folder. 

<h3>Speech-Dispatcher configuration</h3> 

Removed “#” from the file for the modules -( espeak-ng, flite, rhvoice and pico-generic) 
```
nano /etc/speech-dispatcher/speechd.conf
```
<h3>Automatic system update disable</h3> 

1.Package list 

```
nano /etc/apt/apt.conf.d/10periodic 
```
in the file change:
```
APT::Periodic::Update-Package-Lists "0"; 
```
 

2.Auto-update 
```
nano /etc/apt/apt.conf.d/20auto-upgrades 
```
in the file change:
```
APT::Periodic::Update-Package-Lists "0"; 

APT::Periodic::Unattended-Upgrade "0"; 
```
  

3.Remove packages for apport crash report 
```
apt-get remove apport apport-gtk 
```
4. Remove Update-Manager 
```
apt-get remove update-manager-core 
```
5. Remove Celluloid and Rhythmbox 
```
apt-get remove celluloid rhythmbox 
```
6. Remove Webcamoid (not accessible) 
```
apt-get purge webcamoid webcamoid-data webcamoid-plugins 
```
7. Setting Logout Short key - *Alt+Ctrl+Backspace*(click next until you find a yes or no question click yes to apply changes) 
```
dpkg-reconfigure keyboard-configuration 
```

8. Disable preload by default 

  1. Checking preload status 
```
    systemctl is-enabled preload 
```
  2. Disable Preload 
```
    systemctl disable preload
```
<h3>Grub configuration</h3> 

1.Background (create a file named grub in the path specified) 
```
nano /etc/default/grub 
```
Then add the below to the file: 
```
GRUB_INIT_TUNE="2000 400 4 0 1 500 4 0 1 600 4 0 1 800 6 0 1 800 8" 

GRUB_BACKGROUND="/usr/share/Coconut/grub.png"
```
2. Microphone noise reduction script 

• Check script “ microphone_realtime_background_noise_reduction.sh” 

 in 

/usr/share/Coconut/ 

• If not Copy and paste 

 

3. Microphone noise reduction Launcher 

• Check file “ microphone_realtime_background_noise_reduction.desktop” 

 in 

/usr/local/share/applications/ 

• If not Copy and paste 


<h3>Default Configurations and for the first Run</h3> 

When every user created, we must give common application configurations 

1. Copy - NB : don’t copy and paste (. bash_logout, .bashrc, .profile) and 

don’t alter the existing files (. bash_logout, .bashrc, .profile) in the new 

AC — read 15th point(what I've done here is copied the files from old AC except the files mentioned above ) 

/etc/skel 

1. Press Ctrl+H to visible Hidden files 

2. open .config there will a directory named autostart inside that there 

will be 4 files 

1. artha.desktop 

2. canberra-gtk-play.desktop - which we used to play initial music 

3. firstrun.desktop 

4. transmission-gtk.desktop 

3. Templates - for caja file manager context menu 

4. User Guide 

5. open artha.conf in .conf 
```
Notifications=false 
```
6. preferences.cfg in .lios(lios) 
```
run_text_cleaner = 1 

language = 3 

speech-language = 12 
```
7. open .config/ubuntu-mate/welcome/preferences.json 

Add this line(Welcome message disable) 
```
{ 

    "autostart": false, 

    "hide_non_free": false, 

    "show_welcome": false 

} 

 ```

8. .curlew
   1. Curlew configuration file for setting current folder as destination directory 
   2. Play sound after finish
   3. replace with UUSSEERR 

9. LMMS
   1 ~/Documents/lmms
   2 .lmmsrc.xml Basic LMMS configuration 
   3 replace with UUSSEERR 

10. .config/vlc/vlcrc
    1.Starting dialog
    2. Volume 

11. .config/smplayer/smplayer.ini 
```
volume=100 
```
12. .config/uGet/category/0000.json
    1. Download directory 

13. .local/share/orca not copied  
  1 - Rate -> 65  
  2 - shortcuts for increasing and  decreasing orca speed(UP/Down), pitch(Right/Left), Volume(Home/End) 
	3 - Orca preferences default voice to English (Great Britain) (Denis)  
  4 - Orca speak mnemonics, child position enablded, Beep updates enablded  
  5  - SBW orca preferences ( Disable key echo and Enable echo by character)
	6 - sayAllStyle changed to sentence using full stop 

14. Default Applications setted using prefered applications
    1.Copy /skel/.config/mimeapps.list 

15. Do not copy/include - 1 .bash_logout 2 .bashrc 3 .profile

<h3>Script to run after user creation added</h3> 

1. Copy adduser.local file from old AC to new AC same path OR 

/usr/local/sbin/ 

Create a file adduser.local in the above path and copy the below 
```
# $1-username $2-uid $3-gid $4-home-directory-without-trailing-slash 

# Setting lmmsrc file 

sed -i 's/UUSSEERR/'"$1"'/g' $4/.lmmsrc.xml 

# Setting curlew configurations file 

sed -i 's/UUSSEERR/'"$1"'/g' $4/.curlew/curlew.cfg 

# Setting smplayer configurations file 

sed -i 's/UUSSEERR/'"$1"'/g' $4/.config/smplayer/smplayer.ini 
```
2. Give execute permission 
```
chmod +x /usr/local/sbin/adduser.local
```

<h3>User Guide</h3> 

Add Coconut-slideshow user guide, 
1. Slideshow Check for Slideshow.py in 

/usr/share/Coconut/ 

if not Copy and paste 

2. Uncheck Auto removal of ubiquity-slideshow-ubuntu-mate  
```
  apt-mark manual ubiquity-slideshow-ubuntu-mate 
```
3.Uncheck auto removal of gparted 
```
  apt-mark manual gparted
```
<h3>Boot Logo, Grub and Slideshow</h3> 

1. Plymouth boot title 

Edit title to Accessible-Coconut in ubuntu-mate-plymouth; 

Path: 
```
nano /usr/share/plymouth/themes/ubuntu-mate-text/ubuntu-mate-text.plymouth  
```
2. Logo 

Copy and paste logo from old AC to new AC, you can locate logos in the 

Path: /usr/share/plymouth/themes/ubuntu-mate-logo/ 

1. Replace ubuntu-mate-logo.png with coconut logo

2. Replace ubuntu-mate-logo16.png with coconut logo

3. Edit boot selection screen name to AC 

Open cubic-Press Next Button-select Boot 
edit grub.cfg and loopback.cfg  
Replaced “quiet splash” with “textonly"; also change the Ubuntu-mate to Accessible-Coconut 

4. Change - Ubiquity installer icon 

in /usr/share/icons/Yaru 

find all ubiquity.jpg in next all folders like 22x22, 44x44@... etc replace with  AC logo  same directory ubiquity.jpg


<h3>Mate-User-Manager 1.7 installed</h3>  

packages group-service_1.3.0-3_amd64.deb  libgroup-service1_1.3.0-3_amd64.deb  mate-user-admin_1.7.0-1_amd64.deb downloaded from ubuntu repository 
```
 apt install mate-user-admin group-service libgroup-service1
```
<h3>Launchers inside User-Guide marked as trusted</h3> 

Following line added to /etc/skel/firstrun.sh 
```
for i in ~/Desktop/User-Guide/*.desktop; do gio set "$i" "metadata::caja-trusted-launcher" true ;done
```
<h3>Sharada-Braille-Writer auto-new-line disabled</h3>   

Checked the auto-new-line is disabled in .sbw/user_preferences.cfg 
```
  auto-new-line=0 
```
echo-by-word enabled in orca preferences 

/etc/skel/.local/share/orca/app-settings/sharada-braille-writer.conf 
```
echobyword=true
```
<h3>Installed following packages (for Telegram purple alternate)</h3>  
(this was installed manually; but you can follow the steps in the below  GitHub readme file; link: https://github.com/ars3niy/tdlib-purple?tab=readme-ov-file to install if the steps are not working then please install it manually,always download the latest version,libpurple telegram deends on the libssl1 and libwebp6) 

1.libssl1.1_1.1.1f-1ubuntu2_amd64.deb 
Download the package from the specified link: 
https://launchpadlibrarian.net/475574732/libssl1.1_1.1.1f-1ubuntu2_amd64.deb 

Move the downloaded file to Coconut Folder and unpack: 
```
dpkg –i libssl1.1_1.1.1f-1ubuntu2_amd64.deb 
```
Fix any dependency issues (if necessary); If there are dependency issues, run: 
```
sudo apt-get install -f 
```
 

2.libwebp6_0.6.1-2.1+deb11u2_amd64.deb 

Download the libwep6 from the link: 
http://ftp.us.debian.org/debian/pool/main/libw/libwebp/libwebp6_0.6.1-2.1+deb11u2_amd64.deb 

Move the downloaded file to coconut folder and unpack: 
```
dpkg –i libwebp6_0.6.1.2.1+debu11u2_arm64.deb 
```
3. Install libpurple-telegram-tdlib_0.8.1-1_amd64(this is the main package and the rest are packages that this package are depended on) 

Download the package: 
You can download it from a reliable source or repository provided in the below link:  
https://download.opensuse.org/repositories/home:/ars3n1y/Debian_11/amd64/ 

Install the package; Open your  cubic and navigate to the directory where the .deb file is located(coconut folder): 
```
 dpkg -i libpurple-telegram-tdlib_0.8.1-1_amd64.deb 
 ```

<h3>Downgraded Libreoffice to 7.0.6.2_2 amd64 for IBus Braille-Compatibility</h3> 
(Checked Ibus-Braille with LibreOffice 24.8.3 but the problem persists as it is that is the space, and new line is not working as intended it gets attached to the previous word while typing.) 
So, Downgrading is the option; 

Package downloaded from https://downloadarchive.documentfoundation.org/libreoffice/old/ 
1.remove existing libreoffice packages 
```
apt remove  --purge libreoffice* 
apt autoremove --purge 
```
2.Download the file from the respective link:
https://downloadarchive.documentfoundation.org/libreoffice/old/7.0.6.2/deb/x86_64/LibreOffice_7.0.6.2_Linux_x86-64_deb_sdk.tar.gz and paste it in the coconut folder  

LibreOffice_7.0.6.2_Linux_x86-64_deb.tar.gz 

3.Unzip and install the package 

To unzip the file: 
```
tar -xvzf LibreOffice_7.0.6.2_Linux_x86-64_deb.tar.gz 
```
Now navigate to the path: 
Libreoffice_7.0.6.2_Linux_x86-64_deb.tar.gz/DEBS/ 

Then install all deb packages and fix dependencies and verify installation: 
```
dpkg –i *.deb 

apt install –f 

apt search libreoffice
```
<h3>Grub customizer added</h3> 

```
add-apt-repository ppa:danielrichter2007/grub-customizer 
apt-get install grub-customizer 
```
