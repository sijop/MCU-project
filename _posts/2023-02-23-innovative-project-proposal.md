---
layout: post
title: Innovation Project Proposal
author: [Sung-Ping Chen]
category: [Lecture]
tags: [jekyll, ai]
---

This homework is to specify a Future Home application and describe the key features, list all Design Considerations and the required technologies, then draw the System Block Diagram.

---
## 居家整潔機器人
### 應用功能說明
1. 能依照規劃移動並監控家中狀態
2. 能單方面傳送影像及雙方傳送聲音
3. 可遠端餵食家中貓狗
4. 清掃灰塵及簡單拖地

### 設計考量與相關技術
**系統設計考量：**<br>
1. 移動方式:兩輪或四輪移動
2. 供電方式:裝備電池或自行前往充電區充電
3. 聯網方式: WiFi 或 BLE 至手機或電腦

**所需相關技術：**
1. 偵測與控制: MPU6050 
2. 影像辨識: Jetson Nano 
3. 路線規劃: 手機或筆電(連接藍芽或網路)
4. 影像傳輸: ESP32-CAM模組

### 系統方塊圖
![](https://github.com/sijop/MCU-project/blob/main/images/%E5%BE%AE%E8%BB%9F%E9%AB%94%E6%A8%B9%E6%9E%9D%E5%9C%96.jpg?raw=true)

<br>
<br>


*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


