# 指纹密码输入器（ZW111 Fingerprint Keyboard）

ZW111 指纹模块 + ESP32-S3 / ESP32-C3 的指纹宏键盘。验证指纹后，设备通过 USB 或蓝牙 HID 输入你配置的文字、等待和功能键。

## 下载新版

请进入 [Releases](https://github.com/GeofforyTsang130/zw111-fingerprint-keyboard/releases) 下载最新版。主目录只保留源码、接线图和说明。

## 接线

![ZW111 与 ESP32-S3 / C3 通用接线图](docs/zw111-s3-wiring.svg)

ZW111 使用五条功能线：VCC、GND、TX、RX、TOUCH。VCC 接 3.3V，GND 共地，TOUCH 接 GPIO4。串口必须交叉连接。

- S3：模块 TX → GPIO44，模块 RX → GPIO43
- C3：模块 TX → GPIO20，模块 RX → GPIO21
- 振动马达模块：VCC → 5V，GND → GND，IN → GPIO4

振动马达的供电线接 5V，控制输入线接 GPIO4。接线前断电，并以模块丝印为准确认线序。

## 安装和使用

1. 在 Releases 下载安装器 1.2.7。
2. USB 连接开发板，选择 S3 或 C3，首次刷写时按住 BOOT、点按 RST、松开 BOOT。
3. 点击一键安装，完成后在 macOS 蓝牙设置中配对。
4. 使用管理器 1.0.7 录入指纹、编辑宏、切换模式和重启设备。

宏会以明文保存在设备上，请不要保存重要账号密码。

## 校验文件

```text
ecb12116825ec8eb63f277edd732953ca1f6dfebe2e93188d2cd2284ffaac0f1  指纹管理器-1.0.7.zip
a2579fdb8d85b7414f96b5ebaa565c7fa191a06451f58db8a368d371a52aeb53  ZW111-Mac-Installer-1.2.7.zip
```
