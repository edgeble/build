# Build

## source

```shell
mkdir ~/neu6b-sdk && cd ~/neu6b-sdk
git clone -b stable-5.10-rock5 https://github.com/edgeble/u-boot
git clone -b linux-5.10-gen-rkr3.4 https://github.com/edgeble/kernel
git clone -b master https://github.com/rockchip-linux/rkbin
git clone -b debian https://github.com/edgeble/build
git clone -b main https://github.com/edgeble/debos
```

## export toolchain

```shell
export PATH=/toolchain/path/upto/bin:$PATH
```

## u-boot

```shell
cd ~/rk3588-sdk
./build/mk-uboot.sh rk3588-neu6b
```

Program flash
```shell
cd out/u-boot
sudo dd if=./idbloader.img of=/dev/sdX bs=512 seek=64
sudo dd if=./u-boot.itb of=/dev/sdX bs=512 seek=16384
```

## kernel

```shell
cd ~/rk3588-sdk
./build/mk-kernel.sh rk3588-neu6b
```
```shell
ls out/kernel/
Image  rk3588-edgeble-neu6b.dtb
```
