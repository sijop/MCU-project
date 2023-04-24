---
layout: post
title: 藍牙遙控機器人實作
author: [Richard Kuo]
category: [Lecture]
tags: [jekyll, ai]
---

This project is to implement a bluetooth remote controlled robotcar.

---
## 藍牙遙控機器人
![](https://github.com/rkuo2023/MCU-project/blob/main/images/ESP32_RoboCar.jpg?raw=true)


### 應用功能說明
1. Bluetooth remote control App 
2. two-wheel robocar

### 設計考量與相關技術
**系統設計考量：**<br>
1. 操作方式:藍牙遙控手機App
2. 移動方式:兩輪 
3. 供電方式:鋰電池 3.7V x2
4. 聯網方式:藍牙

**所需相關技術：**
1. MIT App Inventor 2 手機程式設計 
2. Arduino程式設計

**所需相關套件:**
![](https://image.ruten.com.tw/g2/8/d4/16/21440347657238_872.jpg)

### 系統方塊圖
![](https://github.com/fairpus/MCU-Arduinoproject/blob/main/images/btcar.png?raw=true)
### 實作演示

forward
<iframe width="500" height="890" src="https://www.youtube.com/embed/2fNPUtyySTA" title="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

backward
<iframe width="500" height="890" src="https://www.youtube.com/embed/h4vAQ1LCHDg" title="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

turn left
<iframe width="500" height="890" src="https://www.youtube.com/embed/G_I6EDTh9iU" title="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

turn right
<iframe width="500" height="890" src="https://www.youtube.com/embed/BfN3hozVdJY" title="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*


