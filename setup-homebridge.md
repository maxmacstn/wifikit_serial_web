# การเพิ่มเข้า HomeBridge
ตัว WiFiKit Serial สามารถเพิ่มเข้าระบบ Homebridge ผ่านโปรโตคอล MQTT ได้ โดยทำการตั้งค่า MQTT Broker ให้เรียบร้อยก่อนการเพิ่ม

## 1. ติดตั้ง MQTT Broker
สามารถใช้ MQTT Broker ตัวไหนก็ได้ที่คุณชื่นชอบ (แนะนำ Mosquitto) 
แนะนำวิธีการติดตั้งตาม [ลิงก์นี้](http://www.raspberryhome.net/article/5/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87-mqtt-broker-%E0%B8%9A%E0%B8%99-raspberry-pi) 

## 2. ติดตั้ง [homebridge-mqttthing](https://github.com/arachnetech/homebridge-mqttthing/tree/master)
1. ติดตั้ง Plugin Homebridge Mqttthing
2. กดตั้งค่า Plugin Mqttthing แล้วเลือก **JSON Config**
   
   ![hb-1](/img/homebridge-conf-1.png ':size=70%')

3. กดเพื่อเพิ่ม Config ใหม่ และเปลี่ยน config ด้านล่างให้ข้อมูลตรงกับระบบของคุณ

![hb-2](/img/homebridge-conf-2.png ':size=70%')

[LABEL](https://gist.githubusercontent.com/maxmacstn/dd6bdd1bbb0d34435badf2838293997a/raw/config.json ':include :type=code')

4. กด Save




## 3. เชื่อมต่อ WiFiKit Serial เข้ากับระบบ
1. ใช้โทรศัพท์ค้นหา Wi-Fi ชื่อ HVAC-XXXXX และเชื่อมต่อ
2. หน้าต่างการ Config จะขึ้นมาอัตโนมัติ หากไม่ชึ้นให้ไปที่ URL `8.8.8.8`
3. ทำการกรอกชื่อ Wi-Fi (SSID) และรหัสผ่าน (PSK) ของ Wi-Fi ที่ต้องการเชื่อมต่อ
4. ทำการกรอกข้อมูล MQTT
- Friendly name/Host name: ชื่ออุปกรณ์ในระบบ ใช้ตัวอักษรภาษาอังกฤษ(a-z), ขีด(-) หรือ underscore (_) เท่านั้น
- Host: หมายเลข IP ของ MQTT Broker
- User: username ของ MQTT ที่ได้ตั้งค่าไว้
- Password: password ของ MQTT ที่ได้ตั้งค่าไว้
5. กด Save & Reboot เพื่อบันทึกค่าและทำการเชื่อมต่อ 
6. ทดสอบสั่งงานจาก HomeKit

*หากตัวโมดูลไม่เชื่อมต่อ หรือไม่หยุดปล่อย Wi-Fi AP แสดงว่าไม่สามารถเชื่อมต่อกับ Wi-Fi ได้*

![ap-screenshot](/img/setup_captive.png ':size=20%')
