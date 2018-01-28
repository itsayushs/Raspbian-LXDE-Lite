# Raspbian-LXDE-Lite
Custom Pre-Build Image File Of Raspbian Lite With GUI [LXDE] and Important URL's 

## Important links:
### To Set-Up and Edit Your WiFi Access Points use this [link](https://learn.adafruit.com/adafruits-raspberry-pi-lesson-3-network-setup/setting-up-wifi-with-occidentalis).
### To Install any other GUI Environment use this [link](https://www.raspberrypi.org/forums/viewtopic.php?t=133691)
### To Download My Pre Build Image [link]()

## Steps to Create Your Own .img file 

- Burn a Raspbian Lite image to your SD card: Which you can download form [here](https://www.raspberrypi.org/downloads/raspbian/).You can use Etcher or Win32DiskImager.
- Insert your SD card and Boot into your Pi.
- after Boot login as **pi** with password **raspberry**
- now login as root.
```
sudo su -
```
- setup your wifi by adding the following lines in  **nano /etc/network/interfaces**
```
auto lo
 
iface lo inet loopback
iface eth0 inet dhcp
 
allow-hotplug wlan0
auto wlan0
 
 
iface wlan0 inet dhcp
        wpa-ssid "ssid"
        wpa-psk "password"
```

- update and upgrade your os.
```
apt-get update
apt-get upgrade
```
- expand your file system use
```
raspi-config
goto to Advanced Options > Expand Filesystem > Yes > Reboot
```
- install Display Server and Login Manager
```
apt-get install --no-install-recommends xserver-xorg
apt-get install --no-install-recommends xinit
```
- install LXDE GUI
```
apt-get install lxde-core lxappearance
```
- install LightDM *optional*
```
sudo apt-get install lightdm
```
- start display server
```
startx
```
- Wola! GUI is Ready 
