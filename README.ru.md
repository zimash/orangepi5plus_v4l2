Работа с OrangePi 5 PLUS 32GB
=============================

```
$ git clone https://github.com/buildroot/buildroot
$ cd buildroot
$ git worktree add ../buildroot.orangepi_5_plus_defconfig # latest commit
$ cd ../buildroot.orangepi_5_plus_defconfig
$ make 
$ make orangepi_5_plus_defconfig
$ make menuconfig # Add BR2_PACKAGE_GST1_PLUGINS_GOOD_PLUGIN_V4L2, BR2_PACKAGE_LIBV4L_UTILS, BR2_PACKAGE_LIBV4L
$ make source
$ make
$ dd if=./output/image/sdcard.img of=/dev/<SDCARDDEV>
```

UART на 3.3В, подключаемся к пинам TTL DEBUG UART.
tio и аналоги на 1.5M

```
$ tio -b 1500000 /dev/ttyUSB0 
```
загружаем и работаем. 


Полезные ссылки:
- [v4l2-ctl - Man Page](https://www.mankier.com/1/v4l2-ctl)
