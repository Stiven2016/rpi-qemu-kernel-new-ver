apt update && apt install qemu-system-aarch64
and after it run this
 qemu-system-aarch64     -M raspi3b     -kernel Image     -dtb bcm2710-rpi-3-b.dtb -drive file=yourosforrpi3b.img ,format=raw,if=sd     -append "rw earlyprintk loglevel=8 dwc_otg.lpm_enable=0 root=/dev/mmcblk0p2 rootdelay=1"     -serial null     -serial mon:stdio     -net user,hostfwd=tcp::5022-:22     -net nic     -m 1024      -device usb-mouse -device usb-kbd 

now 6.6 qemu-system-aarch64     -M raspi3b     -kernel 6.6Image     -dtb 6.6bcm2710-rpi-3-b.dtb -drive file=yourosforrpi3b.img ,format=raw,if=sd     -append "rw earlyprintk loglevel=8 dwc_otg.lpm_enable=0 root=/dev/mmcblk0p2 rootdelay=1"     -serial null     -serial mon:stdio     -net user,hostfwd=tcp::5022-:22     -net nic     -m 1024      -device usb-mouse -device usb-kbd 
