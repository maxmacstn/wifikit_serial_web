# สถานะไฟ LED และการตั้งค่าโมดูล

<img src="../img/components-en.jpeg" style="max-width:500px;width:100%">


## สถานะของไฟ LED

<style type="text/css">
.tg  {border-collapse:collapse;border-color:black;border-spacing:0;}
.tg td{background-color:#fff;border-color:black;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:black;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-hyan{background-color:#34cdf9;text-align:left;vertical-align:top}
.tg .tg-fymr{border-color:black;font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-ncd7{background-color:#81f542;border-color:black;text-align:left;vertical-align:top}
.tg .tg-0pky{border-color:black;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-fymr">ไฟ LED</th>
    <th class="tg-fymr">ติดค้าง</th>
    <th class="tg-fymr">กระพริบ</th>
    <th class="tg-1wig">ดับ</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-ncd7">PWR<br>(สีเหลือง/สีเขียว)</td>
    <td class="tg-0pky">ไฟเข้า โมดูลทำงานปรกติ</td>
    <td class="tg-0pky">Safe Mode</td>
    <td class="tg-0lax">ไฟไม่เข้า หรือโมดูลมีปัญหา</td>
  </tr>
  <tr>
    <td class="tg-hyan">ACT<br>(สีน้ำเงิน)</td>
    <td class="tg-0pky">ไม่สามารถเชื่อมต่อได้/AP Mode</td>
    <td class="tg-0pky">-</td>
    <td class="tg-0lax">การเชื่อมต่อปรกติ</td>
  </tr>
</tbody>
</table>

## ปุ่มสั่งงาน

<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;}
.tg td{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{border-color:black;border-style:solid;border-width:1px;font-family:Arial, sans-serif;font-size:14px;
  font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg .tg-1wig{font-weight:bold;text-align:left;vertical-align:top}
.tg .tg-0lax{text-align:left;vertical-align:top}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg-1wig">เวลาในการกดปุ่ม (วินาที)</th>
    <th class="tg-1wig">การทำงาน</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">&lt; 0.5</td>
    <td class="tg-0lax">เปิด/ปิด แอร์</td>
  </tr>
  <tr>
    <td class="tg-0lax">5 - 15</td>
    <td class="tg-0lax">Reboot โมดูล</td>
  </tr>
  <tr>
    <td class="tg-0lax">&gt; 15</td>
    <td class="tg-0lax">Reset คืนค่าโรงงาน</td>
  </tr>
</tbody>
</table>

## การเปิด/ปิดเสียง Buzzer และ LED
1. เข้าไปที่ IP Address ของตัวโมดูล (สามารถกดที่ปุ่ม VISIT ในหน้า integration)


<img src="../img/mqtt_visit.png " style="max-width:400px;width:100%">


2. ไปที่ Setup -> Unit
3. ตั้ง Beep หรือ LED เป็น ON หรือ OFF
4. กด Save & Reboot

<img src="../img/config-beep-led.png" style="max-width:400px;width:100%">
