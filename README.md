Smart Cycling Helmet (智能骑行头盔)



基于 STM32F103、ESP32 和 Python 的智能骑行头盔系统，集成了姿态检测、GPS 定位、超声波避障、灯光控制以及 PC 端上位机地图显示。



&#x20;项目结构



\- `User/` - STM32 应用层代码（GUI、GPS、MPU6050、WS2812 灯带、超声波等）

\- `Libraries/` - 标准外设库 (StdPeriph Driver) 和 CMSIS 核心文件

\- `Project/RVMDK（uv5）/` - Keil MDK 工程文件（直接双击 `.uvprojx` 打开）

\- `ESP32\_GPS\_Bridge/` - ESP32 桥接程序（用于将 GPS 数据通过 Wi-Fi 转发）

\- `helmet\_1/` - Python 上位机程序（PyQt5 界面 + 地图显示，读取串口/WiFi 数据）



硬件平台



\- 主控：STM32F103 (C8T6 / VE 系列)

\- 姿态传感器：MPU6050 (六轴陀螺仪+加速度计)

\- 定位模块：GPS (NMEA 协议)

\- 测距模块：HC-SR04 (超声波)

\- 灯光：WS2812 (可编程 RGB LED 灯带)

\- 通信：ESP8266 / ESP32 (Wi-Fi 透传)



开发环境



\- MCU 开发\*\*：Keil MDK 5 (UV5) + ARMCC

\- RTOS：RT-Thread (嵌入式实时操作系统)

\- 上位机开发：Python 3.x + PyQt5 + Folium (地图)



快速开始



1\. 编译 STM32 固件

\- 使用 Keil 打开 `Project/RVMDK（uv5）/BH-F103.uvprojx`

\- 编译并下载到目标板



2\. 配置 ESP32 桥接

\- 打开 `ESP32\_GPS\_Bridge/ESP32\_GPS\_Bridge.ino`

\- 修改 Wi-Fi 名称和密码，烧录到 ESP32



3\. 运行 Python 上位机

```bash

cd helmet\_1

pip install -r requirements.txt

python main.py

