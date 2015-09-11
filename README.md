# USB Missile Launcher

Originally by Luke Cole <http://lukecole.name>

http://sourceforge.net/projects/usbmissile
OR
http://lukecole.name/usb_missile_launcher

## Description

USBMissileLauncher is user space Linux driver to control the the USB
Missile Launcher and USB Circus Cannon via the command line or
keyboard (simple C implemenation).

Keyboard Control Keys
---------------------

 * Up Arrow - Move Up
 * Down Arrow - Move Down
 * Left Arrow - Move Left
 * Right Arrow - Move Right
 * F Key - Fire Missile
 * S Key - Stop Moving 

## Installation
============

1. Download the USBMissileLauncher-1.0 code tarball.

2. Uncompress the tarball and untar the code

      tar xvfz USBMissileLauncher-1.0.tgz

3. Go to source directory.

      cd USBMissileLauncher-1.0

4. Remove the usb core modules (requires root/sudo access).
   NOTE: not required for USBMissileLauncher version > 1.0

      sudo rmmod {e,o,u}hci-hcd hid

5. Compile the code

      make

6. Install the code (requires root/sudo access)

      sudo make install

7. Control the USB Missile Launcher from the command line:

      ./USBMissileLauncherUtils -L
      ./USBMissileLauncherUtils -R
      ./USBMissileLauncherUtils -U -S 100
      ./USBMissileLauncherUtils -R -U -F

      This will move the USB Missile Launcher left, right, then up
      however stops after 100ms and then finally moves simutaniously
      right, up and fires a missile.
   
8. Control the USB Missile Launcher from the keyboard located at
   /dev/input/event0:

      sudo ./USBMissileLauncherUtils -c /dev/input/event0
C Linux program to control a USB missile launcher

