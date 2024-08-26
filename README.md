
# Running Your Custom Linux on QEMU

This guide will help you run your custom-built Linux kernel for the Raspberry Pi 3B on QEMU.

## Prerequisites

Make sure you have QEMU installed. You can install it on your system using:

```bash
sudo apt update && sudo apt install qemu-system-aarch64


```bash
qemu-system-aarch64 \
    -M raspi3b \
    -kernel 6.6Image \
    -dtb 6.6bcm2710-rpi-3-b.dtb \
    -drive file=yourosforrpi3b.img,format=raw,if=sd \
    -append "rw earlyprintk loglevel=8 dwc_otg.lpm_enable=0 root=/dev/mmcblk0p2 rootdelay=1" \
    -serial null \
    -serial mon:stdio \
    -net user,hostfwd=tcp::5022-:22 \
    -net nic \
    -m 1024 \
    -device usb-mouse \
    -device usb-kbd

