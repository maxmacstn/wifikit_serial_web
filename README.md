# เกี่ยวกับ WiFiKit Serial

> WiFiKit Serial คือโมดูล Wi-Fi สำหรับเชื่อมต่อเครื่องปรับอากาศเข้ากับระบบ [Home Assistant](https://www.home-assistant.io/) และ [Homebridge](https://homebridge.io/) รองรับเครื่องปรับอากาศที่มีช่อง Serial Interface บนบอร์ดสำหรับสั่งงานจากโมดูลภายนอก เช่น Mitsubishi Mr.Slim และ Daikin

![header](/img/header.jpg)

## ฟีเจอร์
- ชิพประมวลผล ESP32 S3 8MB รองรับ Wi-Fi/BLE
- มี Logic Level Converter เป็น Serial TTL 5V
- รองรับไฟ DC 5V / 7 - 25V
- พอร์ท USB-C สำหรับ Debug และ Upload
- มี Buzzer แจ้งการทำงาน (ปิดได้)
- ไฟ LED แสดงสถานะการทำงาน
- ปุ่มสั่งงาน / ปุ่ม Reset

## Firmware
ตัว Firmware ทำหน้าที่เชื่อมต่อตัวเครื่องปรับอากาศเข้าระบบ Home Assistant ผ่าน MQTT Protocol
ถึงแม้ว่าแอร์ทั้งสองรุ่นจะใช้ Hardware เดียวกัน แต่ว่าตัว Firmware บนบอร์ดนั้นต่างกัน โดยแอร์แต่ละยี่ห้อใช้ Firmware ดังนี้
- Mitsubishi MR.Slim: [mitsubishi2MQTT](https://github.com/maxmacstn/mitsubishi2MQTT)
- Daikin: [daikin2MQTT](https://github.com/maxmacstn/daikin2MQTT)

## ฟังก์ชั่นการทำงานที่รองรับ
ฟังก์ชั่นการทำงานในแต่ละรุ่นอาจจะแตกต่างกัน ขึ้นอยู่กับการรองรับของแอร์รุ่นนั้น ๆ 

### Mitsubishi Mr. Slim
<style type="text/css">
.tg  {border-collapse:collapse;border-color:#ccc;border-spacing:0;}
.tg td{background-color:#fff;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky"><b>Feature<b></th>
    <th class="tg-0pky" colspan="2"><b>Setting<b></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="10">Basic Operation</td>
    <td class="tg-0pky">Power</td>
    <td class="tg-0pky">ON/OFF</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="5">Mode</td>
    <td class="tg-0pky">Auto</td>
  </tr>
  <tr>
    <td class="tg-0pky">Cool</td>
  </tr>
  <tr>
    <td class="tg-0pky">Heat</td>
  </tr>
  <tr>
    <td class="tg-0lax">Dry</td>
  </tr>
    <tr>
    <td class="tg-0lax">Fan Only</td>
  </tr>
  <tr>
    <td class="tg-0lax">Temperature Setting</td>
    <td class="tg-0lax">Temperature adjustment (1°C Step)</td>
  </tr>
  <tr>
    <td class="tg-0lax">Fan Speed Setting</td>
    <td class="tg-0lax">Auto, Quiet, 1, 2, 3, 4</td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Vane Vertical</span></td>
    <td class="tg-0lax">Auto, Swing, 1, 2, 3, 4, 5</td>
  </tr>
  <tr>
    <td class="tg-0lax">Vane Horizontal*</td>
    <td class="tg-0lax">Swing, &lt;&lt;, &lt;, |, &gt;, &gt;&gt;</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2">Status Monitor</td>
    <td class="tg-0lax">Room Temperature</td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Temperature reading (0.5°C Step)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">Power usage*</td>
    <td class="tg-0lax">Watt</td>
  </tr>
</tbody>
</table>

\**รองรับกับเครื่องปรับอากาศบางรุ่น*


### Daikin

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#ccc;border-spacing:0;}
.tg td{background-color:#fff;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-0pky{border-color:inherit;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky">Feature</th>
    <th class="tg-0pky" colspan="2">Setting</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="7">Basic Operation</td>
    <td class="tg-0pky">Power</td>
    <td class="tg-0pky">ON/OFF</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="3">Mode</td>
    <td class="tg-0pky">Cool</td>
  </tr>
  <tr>
    <td class="tg-0pky">Dry</td>
  </tr>
  <tr>
    <td class="tg-0pky">Fan Only</td>
  </tr>
  <tr>
    <td class="tg-0lax">Temperature Setting</td>
    <td class="tg-0lax">Temperature adjustment (0.5°C Step)</td>
  </tr>
  <tr>
    <td class="tg-0lax">Fan Speed Setting</td>
    <td class="tg-0lax">Auto, 1, 2, 3, 4, 5</td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Swing Vertical*</span></td>
    <td class="tg-0lax">Hold, Swing</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="5">Status Monitor</td>
    <td class="tg-0lax">Room Temperature</td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Temperature reading (0.5°C Step)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">Outside Temperature*</td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Temperature reading (0.5°C Step)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">FCU Coil Temperature</td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal">Temperature reading (0.5°C Step)</span></td>
  </tr>
  <tr>
    <td class="tg-0lax">FCU Fan RPM</td>
    <td class="tg-0lax">RPM</td>
  </tr>
  <tr>
    <td class="tg-0lax">Compressor Frequency*</td>
    <td class="tg-0lax">Hz</td>
  </tr>
</tbody>
</table>

\**รองรับกับเครื่องปรับอากาศบางรุ่น*

![ha-screenshot](/img/ha-conf-2.png)
