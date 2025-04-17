# LoRa 数据包转发程序（基于树莓派3B与SX1301芯片）

## 项目概述
本程序基于[lora-net/packet_forwarder](https://github.com/Lora-net/packet_forwarder)二次开发

主要改动文件: ./packet_forwarder/lora_pkt_fwd/src/lora_pkt_fwd.c

改动/重要的地方可以用注释@Description找到

---

## 核心功能
1.定期向终端节点发送下行LoRa数据包
2.接收上行的LoRa数据包


## 使用说明

树莓派内核为Linux rhf2s001 4.4.21-v7+ #911 SMP Thu sep 15 14:22:38 B5T 2016 armv71 GNu/Linux（已上传）

链接: https://pan.baidu.com/s/1DzQ3McugoJUWApPzeCqgzw?pwd=9yiq 提取码: 9yiq

用户名：rxhf
密码：risinghf

需要开启树莓派SPI

sudo raspi-config
interface config
spi
sudo reboot
ls /dev/spidev*          # 确认出现spidev0.0设备节点

git/拷贝完当前程序后，进入程序目录

sudo make clean all完成编译

使用之前确保pktfwd脚本关闭（这个镜像默认安装了）

sudo systemctl stop pktfwd

然后执行编译好的lora_pkt_fwd

./lora_pkt_fwd