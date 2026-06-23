# Setup Board Computer

This section looks at how we are able to connect our board computer, in our case a Raspberry Pi Zero 2 WH, to our flight controller.

## Install MAVLink-router
MAVLink(Micro Air Vehicle Link) is the standard communication protocol used by autopilots to talk to ground control software and companion computers, like our Raspberry Pi.
We need a program that listens for MAVLink traffic on one port and forwards it to others. We use `mavlink-router` for this: https://github.com/mavlink-router/mavlink-router

The packages that we need to install mavlink router are
```
sudo apt install git meson ninja-build pkg-config gcc g++ systemd
```
If we have all packages installed we can download mavlink-router,
```
git clone --recurse-submodules https://github.com/mavlink-router/mavlink-router.git
```
run the meson build inside our downloaded folder
```
cd mavlink-router
meson setup build .
```
and compile and install the files:
```
sudo ninja -C build
sudo ninja -C build instal
```

