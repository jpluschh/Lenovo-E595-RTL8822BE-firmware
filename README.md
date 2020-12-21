# Lenovo E595 RTL8822BE firmware - Linux

Thanks to @samcv, who extracted to binaries from the Lenovo provided firmware for this card.
She also described the steps and the source of the firmware in details in her repo.

samcv/A485-RTL8822BE-firmware


Even though I heard linux kernel should make devices work in general.

For some reason, Bluetooth (Realtek RTL8822BE chip) in my Lenovo E595 was not enabled.

I'm just backing up the steps.

So that the next time I make a clean install on this machine

I don't have to spend a crap ton of time on this again.


### Steps

1. Git clone repo
2. Backup old firmware - wifi and bluetooth
```
sudo cp /lib/firmware/rtlwifi/rtl8822befw.bin /lib/firmware/rtlwifi/rtl8822befw.bin.bak
sudo cp /lib/firmware/rtl_bt/rtl8822b_fw.bin /lib/firmware/rtl_bt/rtl8822b_fw.bin.bak
```
3. Copy new firmware
```
sudo cp rtl8822befw.bin /lib/firmware/rtlwifi/rtl8822befw.bin
sudo cp rtl_bt-rtl8822b_fw.bin /lib/firmware/rtl_bt/rtl8822b_fw.bin
```
4. Reboot

Note: After reboot, still have to put the machine to sleep and then wake it up.

The bluetooth firmware will be loaded after waking up from this sleep.
