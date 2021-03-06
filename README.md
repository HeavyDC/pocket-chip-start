# Pocket-chip start 

## Minimum config
Connect pocketchip by usb (osx)
```Shell Session
ls /dev/tty.usb*
# to list devices 
sudo cu -l /dev/tty.usbmodemxxxxxx -s 115200
```

Config wifi
```Shell Session
sudo nmtui
```

---

## Update from Debian Jessie to Debian Stretch
***Better to stay in jessie for the moment, more stable and omgmog launcher work***
Remove the NTC Servers
```Shell Session
sudo nano /etc/apt/sources.list
```

Process to upgrade from Jessie to Stretch
If you encounter options to chose like /etc/securetty chose de N option "default configuration"
```Shell Session
sudo apt-get upgrade 
sudo apt-get dist-upgrade
sudo sed -i 's/jessie/stretch/g' /etc/apt/sources.list
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
sudo apt-get autoremove
sudo reboot
```

If you need to add key
```Shell Session
sudo apt-key adv --keyserver keys.gnupg.net --recv-key xxxxxxxxxxxxxxxx
```

edit xorg.config 
```Shell Session
sudo nano /etc/X11/xorg.conf
```

Add the following at the end of the file
```
Section "Device"
   	Identifier	"Card0"
   	Driver		"modesetting"   
EndSection
```

case rc.lua error paste assets/rc.lua content
```Shell Session
cd ~/.config/awesome
rm rc.lua
nano rc.lua
```

---

### Locale config
```Shell Session
sudo apt install locales
sudo dpkg-reconfigure tzdata
sudo locale-gen fr_FR fr_FR.UTF-8
```

### Optional 
```Shell Session
sudo apt install openssh-server git python3 python3-pip python-pip
pip install setuptools
pip3 install setuptools
```

### Ressources

[Chip community wiki](http://www.chip-community.org/index.php/Main_Page)
