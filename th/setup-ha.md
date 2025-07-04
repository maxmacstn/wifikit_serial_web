# การเพิ่มเข้า Home Assistant
ตัว WiFiKit Serial สื่อสารกับระบบ Home Assistant ผ่านโปรโตคอล MQTT ตั้งนั้นต้องทำการตั้งค่า MQTT Broker และ MQTT Integration ก่อน หากคุณได้ตั้งค่าเรียบร้อย สามารถข้ามไปยังการเชื่อมต่อโมดูลได้เลย

## วิดีโอการติดตั้ง
<iframe style="width:100% ; aspect-ratio: 16 / 9"  src="https://www.youtube.com/embed/uPHk5j-ZJIM?si=KHFE2BC38sMSddzB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## ขั้นตอนการติดตั้ง

### 1. ติดตั้ง MOSQUITTO MQTT Broker
1. ไปที่ Settings -> Add-ons -> Add-on Store -> Mosquitto Broker
2. กด INSTALL แล้วรอการติดตั้ง
3. กด START
4. กลับมาที่หน้า Settings -> Integration จะเจอ MQTT ขึ้นมาใน Discovered
5. กด Configure แล้วทำตามขั้นตอน

<span style="color:red"> ค่าเริ่มต้นของ Username และ Password ของ MQTT จะเป็นรหัสเดียวกับ Home Assistant </span> <br>  หากต้องการตั้งค่าให้ต่างจากของ Home Assistant ไปที่แท็บ Configuration แล้วตั้ง username และ password ของ mqtt ลงในช่อง `logins` ตามด้านล่าง

```
- username: user
  password: passwd
```

### 2. เชื่อมต่อ WiFiKit Serial เข้ากับระบบ
1. ใช้โทรศัพท์ค้นหา Wi-Fi ชื่อ HVAC-XXXXX และเชื่อมต่อ
2. หน้าต่างการ Config จะขึ้นมาอัตโนมัติ หากไม่ชึ้นให้ไปที่ URL `8.8.8.8`
3. ทำการกรอกข้อมูล Wi-Fi และ MQTT สำหรับการเชื่อมต่อ
- **Hostname**: ชื่ออุปกรณ์ในระบบ <br> <span style="color:red"> *ใช้ตัวอักษรภาษาอังกฤษ(a-z), ขีด(-) หรือ underscore (_) เท่านั้น* </span> 
- **SSID**: ชื่อของ Wi-Fi ที่ต้องการเชื่อมต่อ
- **PSK**: รหัสของ Wi-Fi ที่ต้องการเชื่อมต่อ
- **Friendly Name**: ชื่อที่แสดงผลใน Home Assistant
- **Host**: หมายเลข IP ของ MQTT Broker
- **User:** username ของ MQTT ที่ได้ตั้งค่าไว้
- **Password:** password ของ MQTT ที่ได้ตั้งค่าไว้
4. กด Save & Reboot เพื่อบันทึกค่าและทำการเชื่อมต่อ 
5. เครื่องปรับอากาศจะเข้ามาใน MQTT Integration โดยอัตโนมัติ

*หากตัวโมดูลไม่เชื่อมต่อ หรือไม่หยุดปล่อย Wi-Fi AP แสดงว่าไม่สามารถเชื่อมต่อกับ Wi-Fi ได้*

![ap-screenshot](../img/setup-fields-th.png ':size=100%')
