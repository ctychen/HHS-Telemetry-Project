---
title: Recover SD Card Setup
parent: Setup
has_children: false
nav_order: 1
---


# Recovering an SD Card

If you have a corrupted SD card or some other issue, this is the method for recovering the files on it and setting
up a new card.


1) Mount the bad SD card on another Pi (Plex127), then back up the root partition on to Plex;.
`cp -rf /media/pi/root /home/pi/HHS_bkup/HHS_TX_root_bkup_191108`
(continues even if some files have read errors)


2) Get a new SD card, install NOOBs. Used Rpi GUI desktop to link wifi to Hoinga2, then
perform Raspberry Pi Zero Clean Install per 7/10/19


3) With NOOBS SD card on Plex, Copy over entire HHS subdirectory:
`cp -rf  /home/pi/HHS_bkup/HHS_TX_root_bkup_191108/home/pi/HHS /media/pi/root/home/pi`


Also copy from plex:


`cp -rf  /home/pi/HHS_bkup/HHS_TX_root_bkup_191108/home/pi/.bashrc /media/pi/root/home/pi`




NOW I really need to backup those SD cards, so I found instructions here using Win32DiskImager.exe:
https://raspberrypihq.com/how-to-backup-your-raspberry-pi/

To my PC here:


`[Path]\\HHS_Bkup\\Receiver\\HHS_RX_TestOK_191108.img`, 16GB SD


Also HHS subdirectory and 3 other needed files: HHS_TX_NOOBS&Basic_Config_191109.img


Also made an image of NOOBS with nothing but some basic settings in raspi-config:	16 GB


`[Path]]\\HHS_Bkup\\Transmitter\\HHS_TX_TestOK_191108.img`, 32 GB SD
