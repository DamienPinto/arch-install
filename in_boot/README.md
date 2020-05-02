# In-Boot Actions

Things done during boot that are not included in the Archwiki [installation guide's](https://wiki.archlinux.org/index.php/installation_guide) pre-installation section.

## Network Configuration

Network configuration during boot from live USB installation.

### Create config file for WiFi adapter:

The info used in steps 1 and 2 were found in Kuzeyeu Siarhei's reply to [this](https://askubuntu.com/questions/1081240/wifi-randomly-disconnects-rtl8188ee-ubuntu-18-04) askubuntu post.

1. Use `nano /etc/modprobe.d/rtl8723be.conf` to create config file for my laptop's adapter.
2. Write: `options rtl8723be ips=0 swlps=0 fwlps=0 aspm=0 ant_sel=X`
   - `ant_sel=X`, `X` is either 1 or 2.
   - This is because HP is cheap and only put one antennae on the two possible ports of the WiFi card and you need to tell the system which port to use.
   - Which port gets assigned 1 or 2 is random at boot it seems so just choose one at random. Hope you're feeling lucky punk.
3. Enter command `sudo modprobe -rv rtl8723be` to clear all the drivers the system is currently using.
   - Disclaimer: Not sure this is actually what happens, but this command makes sense in my head and has the desired effect.
4. Enter command `sudo modprobe -v rtl8723be` to reload the "drivers" with the changes you made in steps 1 and 2.
5. Retry:
   - `iwctl station wlan0 scan`
   - `iwctl station wlan0 get-networks`
6. If the expected networks show up: great. If not: repeat steps 2-5 with the `ant_sel` number that you haven't tried.