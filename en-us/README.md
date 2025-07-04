# About WiFiKit Serial

> WiFiKit Serial is a Wi-Fi module for connecting air conditioners to [Home Assistant](https://www.home-assistant.io/) and [Homebridge](https://homebridge.io/). It supports air conditioners with a Serial Interface port on the board for external module control, such as Mitsubishi Electric Mr.SLIM and Daikin.

<img src="../img/components-en.jpeg" style="max-width:500px;width:100%">

## Features
- ESP32 S3 8MB processor, supports Wi-Fi/BLE radio.
- Built-in Logic Level Converter for Serial TTL 5V.
- Supports DC 5V or 7 - 28V power input.
- USB-C port for Debug and Upload.
- Buzzer for operation notification.
- Status LED indicator.
- Setup / Reset button.

## Firmware
We provide the open-source firmware for the module to connect an air conditioner to Home Assistant via MQTT Protocol.

Although the hardware is desiged to support various of air conditioner brands, the firmware needed for each brand is different.

- Mitsubishi MR.Slim: [mitsubishi2MQTT](https://github.com/maxmacstn/mitsubishi2MQTT)
- Daikin: [daikin2MQTT](https://github.com/maxmacstn/daikin2MQTT)

## Supported Functions
The supported functions may vary depending on the air conditioner model.

### Mitsubishi Mr. Slim

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#ccc;border-spacing:0;}
.tg td{background-color:#fff;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;  text-align: left;}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg"><b>Command<b></th>
    <th class="tg" colspan="2"><b>Function<b></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="10">Basic Commands</td>
    <td class="tg-0pky">Operation Status</td>
    <td class="tg-0pky">On/Off</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="5">Operation Mode</td>
    <td class="tg-0pky">Auto</td>
  </tr>
  <tr>
    <td class="tg-0pky">Cool</td>
  </tr>
  <tr>
    <td class="tg-0pky">Heat*</td>
  </tr>
  <tr>
    <td class="tg-0pky">Dry</td>
  </tr>
    <tr>
    <td class="tg-0pky">Fan Only</td>
  </tr>
  <tr>
    <td class="tg-0pky">Target Temperature Setting</td>
    <td class="tg-0pky">Adjustable in 1°C steps</td>
  </tr>
  <tr>
    <td class="tg-0pky">Fan Speed</td>
    <td class="tg-0pky">Auto, Quiet, 1, 2, 3, 4</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">Vertical Swing</span></td>
    <td class="tg-0pky">Auto, Swing, 1, 2, 3, 4, 5</td>
  </tr>
  <tr>
    <td class="tg-0pky">Horizontal Swing*</td>
    <td class="tg-0pky">Swing, &lt;&lt;, &lt;, |, &gt;, &gt;&gt;</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="2">Information</td>
    <td class="tg-0pky">Room Temperature</td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">0.5°C resolution</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">Power Consumption*</td>
    <td class="tg-0pky">Watt</td>
  </tr>
</tbody>
</table>

\**Supported on some air conditioner models*

### Daikin
RA = Room Air, SkyAir = Cassette Type

<style type="text/css">
.tg  {border-collapse:collapse;border-color:#ccc;border-spacing:0;}
.tg td{background-color:#fff;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;overflow:hidden;padding:10px 5px;word-break:normal;}
.tg th{background-color:#f0f0f0;border-color:#ccc;border-style:solid;border-width:1px;color:#333;
  font-family:Arial, sans-serif;font-size:14px;font-weight:normal;overflow:hidden;padding:10px 5px;word-break:normal;  text-align: left;}
</style>
<table class="tg">
<thead>
  <tr>
    <th class="tg"><b>Command<b></th>
    <th class="tg" colspan="2"><b>Function<b></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="9">Basic Commands</td>
    <td class="tg-0pky">Operation Status</td>
    <td class="tg-0pky">On/Off</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="4">Operation Mode</td>
    <td class="tg-0pky">Cool</td>
  </tr>
  <tr>
    <td class="tg-0pky">Dry</td>
  </tr>
  <tr>
    <td class="tg-0pky">Heat*</td>
  </tr>
  <tr>
    <td class="tg-0pky">Fan Only</td>
  </tr>
  <tr>
    <td class="tg-0pky">Target Temperature Setting</td>
    <td class="tg-0pky">RA: Adjustable in 0.5°C steps <br> SkyAir: Adjustable in 1°C steps</td>
  </tr>
  <tr>
    <td class="tg-0pky">Fan Speed</td>
    <td class="tg-0pky">Auto, 1, 2, 3, 4, 5</td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">Horizontal Swing*</span></td>
    <td class="tg-0pky">RA: Hold, Swing <br>SkyAir: Swing,1,2,3,4,5</td>
  </tr>
    <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">Vertical Swing*</span></td>
    <td class="tg-0pky">RA: Hold, Swing <br>SkyAir: Not supported</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="7">Information</td>
    <td class="tg-0pky">Room Temperature</td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">0.5°C resolution</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">Outdoor Temperature*</td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">0.5°C resolution</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">FCU Temperature</td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal">0.5°C resolution</span></td>
  </tr>
  <tr>
    <td class="tg-0pky">FCU Fan Speed</td>
    <td class="tg-0pky">RPM</td>
  </tr>
  <tr>
    <td class="tg-0pky">Compressor Frequency*</td>
    <td class="tg-0pky">Hz</td>
  </tr>
    <tr>
    <td class="tg-0pky">Power Consumption*</td>
    <td class="tg-0pky">kWh</td>
  </tr>
  </tr>
    <tr>
    <td class="tg-0pky">Error Code</td>
    <td class="tg-0pky">Two digits/Four digits</td>
  </tr>
</tbody>
</table>

\**Supported on some air conditioner models*

### Example of device page in MQTT integration.
![ha-screenshot](../img/ha-conf-2.png)

