# OpenHarmony LiteOS-M 移植与物联网控制项目
> 基于 OpenHarmony LiteOS-M，在 STM32 平台完成内核移植、底层驱动开发、WiFi-MQTT 物联网通信与网页控制原型。

## 📌 项目简介
本项目是嵌入式物联网综合实践项目，完成从 OpenHarmony 轻量系统定制编译、内核裁剪、底层驱动适配，到无线网络接入、MQTT 消息通信、Web 端远程控制的完整链路开发。
硬件主控：STM32；WiFi 模组：ESP8266（AT指令）；内核：LiteOS-M。

## ✨ 主要功能
1. OpenHarmony 产品定制：编写 `ohos.build` / `BUILD.gn`，hb 编译框架搭建，Kconfig 内核裁剪、编译排错
2. 底层驱动适配：GPIO、PWM、I2C、看门狗、UART（DMA 队列收发）驱动封装
3. WiFi 子系统：ESP8266 AT 驱动，支持 STA 联网、AP 热点
4. 物联网协议：移植 MQTTPacket + cJSON，JSON 报文编解码
5. 服务与穿透：EMQX MQTT 服务 + cpolar 内网穿透，实现远程上下行通信
6. 上位交互：WebSocket 网页控制面板，下发指令、实时回传设备状态
7. 整机联调：软硬件联合调试，整理移植踩坑记录

## 📂 仓库结构
# 编译截图、硬件实物图、抓包截图
连接后可以通过网页控制开发板，开发板也可以影响网页。
<img width="341" height="255" alt="image" src="https://github.com/user-attachments/assets/10be1fc5-5a18-4998-90f5-acffb196d80c" />

<img width="943" height="683" alt="image" src="https://github.com/user-attachments/assets/5069feef-1d6c-4d98-ac6b-6a0d58f54102" />


## 🛠️ 开发环境
- 系统：Ubuntu
- 编译工具：hb（OpenHarmony 构建工具）
- 内核：OpenHarmony LiteOS-M
- 硬件：STM32 + ESP8266
- 服务：EMQX、cpolar

## 📖 快速说明
1. 使用 `hb set` 选择产品，`hb build` 交叉编译
2. 驱动基于 LiteOS-M IPC 机制（任务、信号量、队列）开发
3. ESP8266 通过 AT 指令封装 WiFi 接口
4. MQTT 负责设备和服务端通信，网页通过 WebSocket 和服务端交互
5. docs 文件夹包含完整实习日志、项目总结、踩坑文档

## ⚠️ 说明
本项目为课程实习实践项目，用于学习 OpenHarmony 轻量系统移植、嵌入式驱动、物联网通信开发。

## 📝 项目总结
项目覆盖轻量系统从源码编译、内核裁剪、底层驱动，到无线网络、MQTT 消息、Web 远程控制的全流程。开发过程中熟悉了 LiteOS-M 内核 IPC、DMA 串口收发、AT 模组驱动、JSON 报文处理、内网穿透等技术，积累了嵌入式软硬件联调、编译报错排查的经验。

## 📄 License
仅供学习参考
