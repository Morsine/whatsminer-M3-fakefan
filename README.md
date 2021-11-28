# Whatsminer Fake Fan
This script emulates fan speed values for cgminer and system (all that reading speed by /sys/class/fanspeed/ path)

# Root Permission
By default, the system doesn't give you root permission, however you'll need root permission in order to install this script

# Installation
As a zero step you need to be able to edit system files, if you never run `mount -o remount,rw /` command, you should do this. That makes you able to write to ASIC filesystem, by default it is read only.

## Fake Fan Installation
1. Copy **fake_fan_initd** from repo to the ASIC filesystem to `/etc/init.d/` directory using `scp` (for example `scp fake_fan_initd 192.168.1.120:/etc/init.d/fakefan`).
2. Run `chmod +x /etc/init.d/fakefan`.
3. Enable service `/etc/init.d/fakefan enable`. Script will start automatically after each boot.

## Required system modification
Please replace the file under /etc/config/fans with the file in the repository.

## Note
With this emulation intake and outtake (both), fans can be disconnected, there's no any checks that fans are installed, only cgminer will check the speeds of fans and prevent miner from starting without working fans.

## Disclaimer
I'm not responsible for anything, You're doing this at your own risk. If you used my code and instructions and come to me telling me you ended up bruning down your home, I'll point my fingure at you and laugh.

Feel free to contact me through issues.
