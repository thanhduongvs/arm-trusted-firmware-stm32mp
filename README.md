# arm-trusted-firmware-stm32mp

## 1. Cài đặt toolchain
- STM32MP1 OpenSTLinux Developer Package `https://www.st.com/content/st_com/en/products/embedded-software/mcu-mpu-embedded-software/stm32-embedded-software/stm32-mpu-openstlinux-distribution/stm32mp1dev.html`
- Chọn **Yocto SDK** để download *en.SDK-x86_64-stm32mp1-openstlinux-5.4-dunfell-mp1-20-06-24.tar.xz*
- `tar -xvf en.SDK-x86_64-stm32mp1-openstlinux-5.4-dunfell-mp1-20-06-24.tar.xz`
- `cd stm32mp1-openstlinux-5.4-dunfell-mp1-20-06-24/sdk`
- `cd stm32mp1-openstlinux-5.4-dunfell-mp1-20-06-24/sdk`
- `./st-image-weston-openstlinux-weston-stm32mp1-x86_64-toolchain-3.1-openstlinux-5.4-dunfell-mp1-20-06-24.sh`
- Chọn đường dẫn gải nén **~/toolchain/openstlinux-5.4-dunfell**
- `vim ~/.bashrc`
- thêm dòng này ở cuối file `export PATH=$PATH:~/toolchain/openstlinux-5.4-dunfell/sysroots/x86_64-ostl_sdk-linux/usr/bin/arm-ostl-linux-gnueabi`
- `source ~/.bashrc`
- Check version `arm-ostl-linux-gnueabi-gcc --version`

## 2. Build arm-trusted-firmware
- `git clone https://github.com/thanhduongvs/arm-trusted-firmware-stm32mp.git`
- `cd arm-trusted-firmware-stm32mp`
- `make CROSS_COMPILE=arm-ostl-linux-gnueabi- PLAT=stm32mp1 ARCH=aarch32 ARM_ARCH_MAJOR=7 AARCH32_SP=sp_min STM32MP_SDMMC=1 STM32MP_EMMC=1 STM32MP_RAW_NAND=1 STM32MP_SPI_NAND=1 STM32MP_SPI_NOR=1 DTB_FILE_NAME==stm32mp157c-kmtek-octavo`

## 3. Link tham khảo
1. https://github.com/STMicroelectronics/arm-trusted-firmware/blob/v2.2-stm32mp/docs/plat/stm32mp1.rst