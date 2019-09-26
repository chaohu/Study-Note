# AliOS-Things之Developer kit 开发板学习笔记

[![Author](https://img.shields.io/badge/author-chaohu-lightgrey.svg)](https://github.com/chaohu)

# developerkit开发板上programming等闪烁时代表未连接
# 烧录程序至开发板时，需注意USB权限问题
# 开发板使用usb口虚拟串口，故连接上usb线即可使用串口
# 查看串口输出时，需注意串口权限问题
# dmesg可查看到开发板所使串口号

# 1、配置：aos make helloworld@developerkit -c config

# 2、编译：aos make

# 3、烧录：aos upload helloworld@developerkit

# 4、查看串口输出：
## 方式1：aos monitor /dev/串口号 BAUD
## 方式2：cutecom
## 方式3：minicom
## 注意：developerkit波特率为115200
