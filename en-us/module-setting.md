# LED Status and Module Settings

<img src="../img/components-en.jpeg" style="max-width:500px;width:100%">

## LED Status

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
    <th class="tg-fymr">LED</th>
    <th class="tg-fymr">Solid</th>
    <th class="tg-fymr">Blinking</th>
    <th class="tg-1wig">Off</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-ncd7">PWR<br>(Yellow/Green)</td>
    <td class="tg-0pky">Power on, module working normally</td>
    <td class="tg-0pky">Safe Mode</td>
    <td class="tg-0lax">No power or module issue</td>
  </tr>
  <tr>
    <td class="tg-hyan">ACT<br>(Blue)</td>
    <td class="tg-0pky">Cannot connect / AP Mode</td>
    <td class="tg-0pky">-</td>
    <td class="tg-0lax">Normal connection</td>
  </tr>
</tbody>
</table>

## Control Button

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
    <th class="tg-1wig">Button Press Duration (seconds)</th>
    <th class="tg-1wig">Action</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax">&lt; 0.5</td>
    <td class="tg-0lax">Turn air conditioner ON/OFF</td>
  </tr>
  <tr>
    <td class="tg-0lax">5 - 15</td>
    <td class="tg-0lax">Reboot module</td>
  </tr>
  <tr>
    <td class="tg-0lax">&gt; 15</td>
    <td class="tg-0lax">Factory reset</td>
  </tr>
</tbody>
</table>

## Enabling/Disabling Buzzer and LED

1. Go to the module's IP Address (you can click the VISIT button on the integration page)

<img src="../img/mqtt_visit.png " style="max-width:400px;width:100%">

2. Go to Setup -> Unit  
3. Set Beep or LED to ON or OFF  
4. Click Save & Reboot

<img src="../img/config-beep-led.png" style="max-width:400px;width:100%">
