---
layout: post
title: IoT Thinkspeak
author: [Wei-Sheng Chang]
category: [Lecture]
tags: [jekyll, ai]
---

This homework is to specify a Future Home application and describe the key features, list all Design Considerations and the required technologies, then draw the System Block Diagram.

---
### 方塊圖
![](https://github.com/sijop/MCU-project/blob/main/images/think.jpg?raw=true)

---
### DHT11 溫度和濕度圖
![](https://github.com/sijop/MCU-project/blob/main/images/349235274_104233512683437_8585855723182126524_n.jpg?raw=true)

---
### 程式碼
```
#include <WiFi.h> 

#include "DHT.h"
#define DHTPIN 23

DHT dht(DHTPIN, DHT11, 15);
const char* ssid     = "wifi name";
const char* password = "wifi password";
const char* host = "api.thingspeak.com";
const char* thingspeak_key = "your_Write_API_Key";

void turnOff(int pin) {
  pinMode(pin, OUTPUT);
  digitalWrite(pin, 1);
}

void setup() {
  Serial.begin(115200);

  // disable all output to save power
  
  turnOff(0);
  turnOff(2);
  turnOff(4);
  turnOff(5);
  turnOff(12);
  turnOff(13);
  turnOff(14);
  turnOff(15);

  dht.begin();
  delay(10);
  
  // We start by connecting to a WiFi network
  
  Serial.println();
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);
  
  WiFi.begin(ssid, password);
  
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }

  Serial.println("");
  Serial.println("WiFi connected");  
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
}

int value = 0;

void loop() {
  delay(5000);
  ++value;

  Serial.print("connecting to ");
  
  Serial.println(host);
  
  // Use WiFiClient class to create TCP connections
  WiFiClient client;
  
  const int httpPort = 80;
  
  if (!client.connect(host, httpPort)) {
    Serial.println("connection failed");
    return;
  }

  String temp = String(dht.readTemperature());
  
  String humidity = String(dht.readHumidity());
  
  String url = "/update?key=";
  
  url += thingspeak_key;
  
  url += "&field1=";
  
  url += temp;
  
  url += "&field2=";
  
  url += humidity;
  
  Serial.print("Requesting URL: ");
  
  Serial.println(url);
  
  // This will send the request to the server
  client.print(String("GET ") + url + " HTTP/1.1\r\n" +
               "Host: " + host + "\r\n" + 
               "Connection: close\r\n\r\n");
  delay(10);
  
  // Read all the lines of the reply from server and print them to Serial
  while(client.available()){
    String line = client.readStringUntil('\r');
    Serial.print(line);
  }
  
  Serial.println();
  Serial.println("closing connection. going to sleep...");
  delay(1000);
  // go to deepsleep for 1 minutes
  //system_deep_sleep_set_option(0);
  //system_deep_sleep(1 * 60 * 1000000);
  delay(1*10*1000);
}
```
<br>
<br>

*This site was last updated {{ site.time | date: "%B %d, %Y" }}.*

