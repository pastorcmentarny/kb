1. Insert USB stick.
2. run the command 'lsusb' to find  ID of USB stick.
```bash
$ lsusb
Bus 001 Device 001: ID d00e:8686 Usb Stick
Bus 001 Device 002: ID 42e1:4554 Realtek Semiconductor Corp. RTL8188CUS 802.11n WLAN Adapter
```
3. ID is split into vendor(d00e) and product(8686)
4. `sudo nano /etc/udev/rules.d/10-poweroff.rules`
5. add  `ACTION=="add", ATTRS{idVendor}=="d00e", ATTRS{idProduct}=="8686", RUN+="/sbin/poweroff"` 
6. Save it.
7. Remove the USB stick.
8. `sudo udevadm control --reload-rules`
9. Insert the USB stick. (Raspberry Pi)
