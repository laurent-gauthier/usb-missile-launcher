# USB Missile Launcher

This code was originally written by Luke Cole (see http://lukecole.name).

I have just imported it in GIT from the original Sourceforge project and
made some cosmetic changes to it:

* http://sourceforge.net/projects/usbmissile

The original GPLv2 license is used, as it should.

## Description

**usb-missile-launcher** is user space Linux driver to control the the USB
Missile Launcher and USB Circus Cannon from the command line or via
keyboard (simple C implementation).

Command Line Control Options:

* -F: Fire one missile (that's what it's all about!).
* -R: Turn the turret towards the right.
* -L: Turn the turret towards the left.
* -U: Turn the turret up.
* -D: Turn the turret down.

In addition to these commands it possible to specify a delay after which the
execution of the command is to be stopped:

* -S **delay**: The delay value has to be expressed in milliseconds.

Keyboard Control Keys:

* Up Arrow - Move Up
* Down Arrow - Move Down
* Left Arrow - Move Left
* Right Arrow - Move Right
* F Key - Fire Missile
* S Key - Stop Moving 

## Installation

On Ubuntu you first need to install the libusb-dev package before you
can compile this program.

1. Clone this GIT repository from Github:

      ```
      git clone https://github.com/laurent-gauthier/usb-missile-launcher
      ```

3. Go to source directory:

      ```
      cd usb-missile-lancher
      ```

4. Compile the code:

      ```
      make
      ```

5. Control the USB Missile Launcher from the command line, as root:

      ```
      ./usb-missile-launcher -L
      ./usb-missile-launcher -R
      ./usb-missile-launcher -U -S 100
      ./usb-missile-launcher -R -U -F
      ```

      This will move the USB Missile Launcher left, right, then up
      however stops after 100ms and then finally moves simultaneously
      right, up and fires a missile.
   
Alternatively is also possible to control the USB Missile Launcher
from the keyboard located at /dev/input/event0 as follows:

```
sudo ./usb-missile-launcher -c /dev/input/event0
```

