# การเพิ่มเข้า Home Assistant
ตัว WiFiKit Serial สื่อสารกับระบบ Home Assistant ผ่านโปรโตคอล MQTT ตั้งนั้นต้องทำการตั้งค่า MQTT Broker และ MQTT Integration ก่อน หากคุณได้ตั้งค่าเรียบร้อย สามารถข้ามไปยังการเชื่อมต่อโมดูลได้เลย

## 1. ติดตั้ง MOSQUITTO MQTT Broker
1. ไปที่ Settings -> Add-ons -> Add-on Store -> Mosquitto Broker
2. กด install แล้วรอการติดตั้ง
3. ไปที่แท็บ Configuration แล้วตั้ง username และ password ของ mqtt ลงในช่อง `logins` ตามด้านล่าง

```
- username: user
  password: passwd
```
4. กด START
5. กลับมาที่หน้า Settings -> Integration จะเจอ MQTT ขึ้นมาใน Discovered
6. กด Configure แล้วทำตามขั้นตอน

## 2. เชื่อมต่อ WiFiKit Serial เข้ากับระบบ
1. ใช้โทรศัพท์ค้นหา Wi-Fi ชื่อ HVAC-XXXXX และเชื่อมต่อ
2. หน้าต่างการ Config จะขึ้นมาอัตโนมัติ หากไม่ชึ้นให้ไปที่ URL `8.8.8.8`
3. ทำการกรอกชื่อ Wi-Fi (SSID) และรหัสผ่าน (PSK) ของ Wi-Fi ที่ต้องการเชื่อมต่อ
4. ทำการกรอกข้อมูล MQTT
- Friendly name/Host name: ชื่ออุปกรณ์ในระบบ ใช้ตัวอักษรภาษาอังกฤษ(a-z), ขีด(-) หรือ underscore (_) เท่านั้น
- Host: หมายเลข IP ของ MQTT Broker
- User: username ของ MQTT ที่ได้ตั้งค่าไว้
- Password: password ของ MQTT ที่ได้ตั้งค่าไว้
5. กด Save & Reboot เพื่อบันทึกค่าและทำการเชื่อมต่อ 
6. เครื่องปรับอากาศจะเข้ามาใน MQTT Integration โดยอัตโนมัติ

*หากตัวโมดูลไม่เชื่อมต่อ หรือไม่หยุดปล่อย Wi-Fi AP แสดงว่าไม่สามารถเชื่อมต่อกับ Wi-Fi ได้*

![ap-screenshot](/img/setup_captive.png ':size=20%')
