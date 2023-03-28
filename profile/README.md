## **ความเป็นมาของโครงงาน**   

<h4>เนื่องจากผู้ปกครองของนิสิตในกลุ่มมีอาชีพเสริมคือการทำสวน นิสิตของผู้ปกครองคนดังกล่าวจึงได้ทำการปรึกษาเพื่อนในกลุ่มว่าจะสามารถนำความรู้ที่ได้จากการเรียนมาประยุกต์กับเหตุการณ์นี้ได้อย่างไรบ้าง จึงนึกถึงวิชา Embedded ขึ้นมาและได้ทำการปรึกษาหารือวิธีช่วยลดระยะเวลา การดูแลรักษาสวนของผู้ปกครองนิสิตคนนั้น</h4>

---
# **Features**
<center><img src="https://i.ibb.co/Cby7z35/Screen-Shot-2566-03-25-at-14-49-10.png" style="border-radius: 20px; width: 70%;"/img></center>
<p style="text-align: center; font-weight: bold">สรุป Feature ทั้งหมด</p>

**1. Farm Management System**
เป็นระบบที่สามารถให้เจ้าของไร่สามารถจะจัดการได้ว่าให้แปลงไหนปลูกพืชชนิดอะไรและสามารถใส่ได้ว่าใครเป็นคนรับผิดชอบแปลงนั้นๆ โดยสามารถที่จะควบคุมได้ผ่าน Front-end โดยมี feature ย่อยๆดังนี้

* เพิ่มแปลงใหม่ โดยจะต้องเลือกว่าแปลงนั้นจะปลูกอะไรและใส่ชื่อผู้รับผิดชอบที่ดูแลแปลงนั้น
* เปลี่ยนชื่อผู้ที่รับผิดชอบในแปลงนั้นๆ
* ลบแปลงทิ้ง

**2. Automatic Watering System**
เป็นระบบที่จะคอยรดนำ้ให้กับพืชในแต่ละแปลงแบบอัตโนมัติ โดยค่าความชื้นที่เหมาะสมจะขึ้นอยู่กับว่าในแปลงนั้นปลูกอะไร โดยในฐานข้อมูลจะเก็บข้อมูลว่า พืชชนิดไหนจะเหมาะกับความชื้นในระดับใด

**3. Weather Report**
เป็นระบบจะแสดงผลบนหน้าเว็บว่าสภาพอากาศในบริเวณแปลงนามีสภาพอากาศเป็นอย่างไร เช่น อุณหภูมิ (celsius), ความชี้นในอากาศ และ ปริมาณนำ้ฝน (เนื่องจากว่าการทดสอบจริงจะต้องไปทดสอบในสถาณการณ์จริงซึ่งอาจจะทำให้ Hardware พังได้จึงไม่สามารถ Demo ให้ดูได้)

**4. Plant Status Per Field Report**
เป็นระบบที่จะอ่านค่าความชื้นในดินในแต่ละแปลงและนำมาแสดงผลในหน้าเว็บ

**5. Farm Status Report**
เป็นระบบที่จะคอยตรวจจับสถานะฟาร์มต่างๆเช่น ตรวจสอบควัน, ตรวจสอบเปลวไฟ โดยถ้าเกิดสามารถตรวจจับอย่างใดอย่างนึง และระบบก็จะตรวจสอบด้วยว่าปริมาณนำ้ในถังที่จะใช้ในการรดนำ้ต้นไม้เหลือเท่าไหร่

**6. LCD Weather Report**
จะเป็นการแสดงผลสภาพอากาศบริเวณรอบๆฟาร์ม โดยจะแสดงผลบนจะ LCD

**7. Automatic Gate**
เป็นระบบเปิดปิดเข้าประตูฟาร์มอัตโนมัติ โดยจะใช้ระบบเปิดประตูแบบไร้สัมผัสและมีระบบคอยควบคุมการปิดไม้กั้นเพื่อความปลอดภัยของคนใช้งาน

---
## **Details**

**1. Automatic Watering System**  
โดยระบบรดนำ้ต้นไม้จะใช้อุปกรณ์ Hardware

* [Micro Submersible Water Pump DC 3V-5V](https://th.cytron.io/p-micro-submersible-water-pump-dc-3v-5v)
* [Relay Module 5V 1 Channel HIGH Trigger 250V/10A](https://www.cybertice.com/product/1744/relay-module-5v-1-channel-high-trigger-250v-10a-%E0%B8%9A%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%94-%E0%B8%A3%E0%B8%B5%E0%B9%80%E0%B8%A5%E0%B8%A2%E0%B9%8C-5v-1-%E0%B8%8A%E0%B9%88%E0%B8%AD%E0%B8%87)
* [2xAAA Battery Holder](https://th.cytron.io/p-2xaaa-battery-holder)
* [NODEMCU ESP32](https://th.cytron.io/p-nodemcu-esp32)<br>  
โดย esp32 จะได้ไป subscribe topic ที่ back-end จะ publish สถานะในการรดนำ้ต้นไม้ โดยแต่ละแปลงจะ subscribe ไปยัง topic ของตนเองตามหมายเลขของแปลง
โดยเราจะนำเอา Relay มาคอยควบคุมการจ่ายไฟจากรางถ่านไปยังตัว Pump นำ้

<center><img src="https://i.ibb.co/qdY3P9g/Part4.png" style="border-radius: 20px; width: 100%;"></center>
<p style="text-align: center; font-weight: bold">Automatic Watering System</p>


**2. Plant Status Per Field Report**   
โดยระบบแสดงสถานะในแต่ละแปลงจะใช้อุปกรณ์ Hardware

* [Moisture Sensor Module](https://th.cytron.io/p-moisture-sensor-module#tab-review)
* [NODEMCU ESP32](https://th.cytron.io/p-nodemcu-esp32)<br>
โดย esp32 จะทำการ publish ค่าความชื้นในดินในแต่ละแปลงให้กับ backend และ frontend ค่อยดึงข้อมูลจากฐานข้อมูลและนำไปแสดงผลหน้าเว็บของแต่ละแปลง

<center><img src="https://i.ibb.co/2srrKJd/Part5.png" style="border-radius: 20px; width: 100%;"></center>
<p style="text-align: center; font-weight: bold">Moisture Per Field Report</p>


**3. Weather Report and Farm Status Report**  
โดยเป็นระบบที่จะรายงานสภาพอากาศและสถานะบริเวณรอบๆฟาร์ม โดยจะใช้อุปกรณ์ Hardware  

* [MQ2 Smoke LPG CO Sensor Module](https://th.cytron.io/p-mq2-smoke-lpg-co-sensor-module)
* [5VDC HC-SR04 Ultrasonic Sensor](https://th.cytron.io/p-5v-hc-sr04-ultrasonic-sensor) x2
* [DHT11 Sensor Module Breakout](https://th.cytron.io/p-dht11-sensor-module-breakout?r=1)
* [Infrared IR Flame Detector Sensor Module](https://www.cybertice.com/product/3585/เซ็นเซอร์ตรวจจับเปลวไฟ-infrared-ir-flame-detector-sensor-module-ky-026)
* [NODEMCU ESP32](https://th.cytron.io/p-nodemcu-esp32)<br>  
โดย esp32 จะอ่านค่าจาก sensor ทั้ง 5 ตัว โดยการ publish ข้อมูลจากแยกเป็น 2 topic เพราะเนื่องจากแต่ละ sensor จะมีการส่งข้อมูลไป update มี interval ที่ไม่เท่ากัน. 
    * MQ5 (ตรวจจับขวัน), Flame (ตรวจจับเปลวไฟ), Ultrasonic (ตรวจสอบระดับในถังนำ้สำหรับรดนำ้ต้นไม้) จะถูก publish ไป ทุก 1 วินาที
    * DHT11 (อุณหภูมิและความชื้นในอากาศ), Ultrasonic (ตรวจสอบระดับนำ้ฝน) จะถูก publish ไปทุกๆ 5 วินาที

<center><img src="https://i.ibb.co/Qp3sqMT/Part1.png" style="border-radius: 20px; width: 100%;"/></center>
<p style="text-align: center; font-weight: bold">Weather Report</p>
<center><img src="https://i.ibb.co/cDWL7tC/Part2.png" style="border-radius: 20px; width: 100%;"/></center>
<p style="text-align: center; font-weight: bold">Farm Status Report</p>

**4. LCD Weather Report**  
จะเป็นการรายงานสภาพอากาศบนจอ LCD โดยจะใช้อุปกรณ์ Hardware  

* [1602 LCD (Blue Screen) 16x2 with I2C Interface](https://www.cybertice.com/product/897/1602-lcd-blue-screen-16x2-โมดูลจอแสดงผล-lcd-พร้อม-i2c-interface)
* [NODEMCU ESP32](https://th.cytron.io/p-nodemcu-esp32)<br>  
โดยเราได้ใช้ library [esp_now.h](https://randomnerdtutorials.com/esp-now-esp32-arduino-ide/) ในการส่งข้อมูลข้ามระหว่าง board แบบ wireless โดยจะใช้เพียง [data link layer](https://www.techtarget.com/searchnetworking/definition/Data-Link-layer) ซึ่ง บอร์ดที่อ่านสภาพอากาศและสถานะจะส่งข้อมูลไปหาบอร์ด LCD ทุกๆ 5 วินาทีและบอร์ด LCD ก็จะนำค่าล่่าสุดมาแสดงผลบนจอ

**5.Automatic Gate** 
เป็นบอร์ดที่จะควบคุมการเปิดปิดประตูโดยมี Hardware

* [Laser Head Transmitter Sensor Module](https://th.cytron.io/p-650nm-laser-5v-5mw-module)
* [MG90S Metal Gear Micro Servo](https://th.cytron.io/p-mg90s-metal-gear-micro-servo)
* [LDR](https://th.cytron.io/p-ldr-small)
* [5VDC HC-SR04 Ultrasonic Sensor](https://th.cytron.io/p-5v-hc-sr04-ultrasonic-sensor)
* [HC-SR505 Mini PIR Motion Sensor Module](https://th.cytron.io/p-hc-sr505-mini-pir-motion-sensor-module)<br>

โดยเราจะใช้ระบบไร้สัมผัสในการเปิดประตูโดยจะใช้ servo มาเป็นที่เปิดไม่กั้น ซึ่งสามารถเอามือมา hover รอบ sensor ได้โดยจะใช้ Ultrasonic ในการตรวจสอบว่ามีมือมาบังอยู่รึป่าว และจะใช้ Mini PIR Motion sensor เพื่อตรวจสอบว่าเป็นมือคนจริงๆรึป่าวเพื่อป้องกันการมีวัตถุมาวางขวาง Ultrasonic โดยประตูจะถูกเปิดค้างอย่างน้อย 5 วินาที และการปิดประตูจะมีการตรวจสอบว่ามีวัตถุหรือคนขวางประตูอยู่รึป่าวโดยจะใช้ Laser Emitter และ LDR ในการข่วยตรวจสอบโดยจะตั้งให้ Laser Emitter ส่องตรงไปหา LDR ถ้ามีวัตถุหรือคนขวางอยู่ LDR จะอ่านค่าได้น้อยจะทำให้ประตูยังเปิดค้างไว้อยู่ แต่ถ้าไม่มีวัตถุมาขวาง LDR จะอ่านค่าจาก Laser ได้ตรงและประตูจะปิดทันที

---
**Other Hardware Details**

* โดยในการพัฒนาในส่วนของ Hardware จะใช้ [Arduino IDE](https://www.arduino.cc/en/software) ในการพัฒนา
* ในการเขียนโค้ดจะใช้ Multitasking มาช่วยในการเพิ่มความเร็วและความง่ายในการพัฒนา
* มีการใช้ library เพิ่มเติมสำหรับ sensor แต่ละตัว<br>

**Other Hardware Library**
1. [DHT11.h](https://github.com/adafruit/DHT-sensor-library)
2. [MQ2.h](https://github.com/labay11/MQ-2-sensor-library)
3. [HCSR04.h for Ultrasonic](https://github.com/gamegine/HCSR04-ultrasonic-sensor-lib)
4. [WiFi.h (built-in)](https://randomnerdtutorials.com/esp32-useful-wi-fi-functions-arduino/)
5. [ArduinoJson.h](https://arduinojson.org)
6. [esp_now.h](https://randomnerdtutorials.com/esp-now-esp32-arduino-ide/)
7. [PubSubClient.h](https://pubsubclient.knolleary.net/api)
8. [LiquidCrystal_I2C.h](https://github.com/fdebrabander/Arduino-LiquidCrystal-I2C-library)
9. [ESP32Servo.h](https://www.cybertice.com/article/276/สอนใช้งาน-esp32-es08ma-servo-หมุนแบบ-0-180-องศา)

**อุปกรณ์ที่ใช้**
1. ESP-WROOM-32 x4
2. [NodeMCU ESP32](https://th.cytron.io/p-nodemcu-esp32) x3
3. [Breadboard 8.5x5.5cm (400 Holes)](https://th.cytron.io/c-arduino-ecosystem/c-Accessories-for-Arduino/p-breadboard-8.5x5.5cm-400-holes) เยอะมาก
4. [Moisture Sensor Module](https://th.cytron.io/p-moisture-sensor-module#tab-review) x4
5. [Relay Module 5V 1 Channel HIGH Trigger 250V/10A](https://www.cybertice.com/product/1744/relay-module-5v-1-channel-high-trigger-250v-10a-%E0%B8%9A%E0%B8%AD%E0%B8%A3%E0%B9%8C%E0%B8%94-%E0%B8%A3%E0%B8%B5%E0%B9%80%E0%B8%A5%E0%B8%A2%E0%B9%8C-5v-1-%E0%B8%8A%E0%B9%88%E0%B8%AD%E0%B8%87) x4
6. [2xAAA Battery Holder](https://th.cytron.io/p-2xaaa-battery-holder) x4
7. [MQ2 Smoke LPG CO Sensor Module](https://th.cytron.io/p-mq2-smoke-lpg-co-sensor-module) x1
8. [Micro Submersible Water Pump DC 3V-5V](https://th.cytron.io/p-micro-submersible-water-pump-dc-3v-5v) x4
9. [5VDC HC-SR04 Ultrasonic Sensor](https://th.cytron.io/p-5v-hc-sr04-ultrasonic-sensor) x3
10. [DHT11 Sensor Module Breakout](https://th.cytron.io/p-dht11-sensor-module-breakout?r=1) x1
11. [Infrared IR Flame Detector Sensor Module](https://www.cybertice.com/product/3585/เซ็นเซอร์ตรวจจับเปลวไฟ-infrared-ir-flame-detector-sensor-module-ky-026) x1
12. [1602 LCD (Blue Screen) 16x2 with I2C Interface](https://www.cybertice.com/product/897/1602-lcd-blue-screen-16x2-โมดูลจอแสดงผล-lcd-พร้อม-i2c-interface) x1
13. [Laser Head Transmitter Sensor Module](https://th.cytron.io/p-650nm-laser-5v-5mw-module) x1
14. [MG90S Metal Gear Micro Servo](https://th.cytron.io/p-mg90s-metal-gear-micro-servo) x1
15. [LDR](https://th.cytron.io/p-ldr-small) x1
16. [HC-SR505 Mini PIR Motion Sensor Module](https://th.cytron.io/p-hc-sr505-mini-pir-motion-sensor-module) x1
17. [Resistor 10k]<br>
---
**เครื่องมือที่ใช้ในการพัฒนา**
**Frontend**
* UX/UI Design: [Figma](https://www.figma.com/file/pU4FR98DjN674zZbek822O/Embedded-Project?node-id=0%3A1&t=Rh7ylBnOWwOw1AC4-1)
* Frontend Library: ReactJS, Axios, Bootstrap, SweetAlert2
**Backend**
* database: MongoDB Atlas
* Framework: NodeJS
* Library: express, mqtt , cors, dotenv, express-mongo-sanitize, hpp, morgan, xss-clean

**รายละเอียด Frontend**
* ใช้ Figma ในการออกแบบ User Interface ทั้งหมด
* ใช้ ReactJS ในการพัฒนาเว็บไซต์
* ใช้ Axios ในการทำ HTTP request กับ backend
* ใช้ Bootstrap Modal ในการทำ Popup แสดงกราฟ และ Popup เพิ่มแปลง
* ใช้ SweetAlert2 ในการแสดงแจ้งเตือนและแก้ไขข้อมูลเล็กน้อย
**รายละเอียด Backend**
* Setup configuration ของ Collection และ Data Model ของ MongoDB
* ติดต่อกับ Hardware ด้วย MQTT server เพื่อรับข้อมูลลงไปเก็บใน MongoDB Database ด้วย Library Mongoose และสั่งการรดน้ำ
* ติดต่อกับ Frontend ด้วย HTTP Server เพื่อส่งข้อมูลในการแสดงผล และรับการตั้งค่าการเปิดปิดการใช้งานแต่ละแปลงจาก Frontend
###**รายละเอียด Hardware**
* [Schematics](https://smart-farm-by-wave-schematics.tiiny.site/)
