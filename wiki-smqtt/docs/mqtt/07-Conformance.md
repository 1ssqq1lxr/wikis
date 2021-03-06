---
title: 第七章 一致性 Conformance
---

MQTT规范定义了MQTT客户端实现和MQTT服务端实现的一致性要求

MQTT实现可以同时是MQTT客户端和MQTT服务端。接受入站连接和建立到其它服务端的出站连接的服务端必须同时符合MQTT客户端和MQTT服务端的要求 \[MQTT-7.0.0-1\]。

为了与任何其它的一致性实现交互操作，一致性实现不能要求使用在本规范之外定义的任何扩展 \[MQTT-7.0.0-2\]。

## 7.1 一致性目标 Conformance Targets

### 7.1.1 MQTT服务端 MQTT Server

一个MQTT服务端只有满足下面所有的要求才算是符合本规范：

1. 服务端发送的所有控制报文的格式必须符合第二章和第三章描述的格式
2. 遵守第4.7节描述的主题匹配规则。
3. 满足下列章节中所有**必须**级别的要求，明确仅适用于对客户端的除外：
	- 第一章 – 介绍
	- 第二章 – MQTT控制报文格式
	- 第三章 – MQTT控制报文
	- 第四章 – 操作行为
	- 第六章 –（如果MQTT的网络层是WebSocket）
	- 第七章 – 一致性目标

满足一致性要求的服务端**必须**支持使用一个或多个底层传输协议，只要它提供有序的、可靠的、双向字节流（从客户端到服务端和从服务端到客户端）\[MQTT-7.1.1-1\]。但是一致性并不依赖于它支持任何特定的传输协议。服务端**可以**支持第4.2节列出的任何传输协议，或者任何其它满足 \[MQTT-7.1.1-1\] 要求的传输协议。

### 7.1.2 MQTT客户端 MQTT Client

一个MQTT客户端只有满足下面所有的要求才算是符合本规范：

1. 客户端发送的所有控制报文的格式必须符合第二章和第三章描述的格式
2. 满足下列章节中所有**必须**级别的要求，明确仅适用于对服务端的除外：
	- 第一章 – 介绍
	- 第二章 – MQTT控制报文格式
	- 第三章 – MQTT控制报文
	- 第四章 – 操作行为
	- 第六章 – （如果MQTT的网络层是WebSocket）
	- 第七章 – 一致性目标

满足一致性要求的客户端**必须**支持使用一个或多个底层传输协议，只要它提供有序的、可靠的、双向字节流（从客户端到服务端和从服务端到客户端）\[MQTT-7.1.2-1\]。但是一致性并不依赖于它支持任何特定的传输协议。客户端**可以**支持第4.2节列出的任何传输协议，或者任何其它满足 \[MQTT-7.1.2-1\] 要求的传输协议。


