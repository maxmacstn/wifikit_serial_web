# Adding to HomeBridge

The WiFiKit Serial can be integrated into the Homebridge system via the MQTT protocol. Make sure to set up your MQTT Broker before proceeding.

### 1. Install MQTT Broker
You can use any MQTT Broker you prefer (Mosquitto is recommended). Follow the installation guide at [this link](http://www.raspberryhome.net/article/5/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87-mqtt-broker-%E0%B8%9A%E0%B8%99-raspberry-pi).

### 2. Connect WiFiKit Serial to the System
1. Use your phone to search for a Wi-Fi network named HVAC-XXXXX and connect to it.
2. The configuration page should open automatically. If not, go to the URL `8.8.8.8`.
3. Enter your Wi-Fi and MQTT details for connection:
- **Hostname**: Device name in the system <br> <span style="color:red"> *MQTT Hostname should contain only alphanumeric (aA-zZ, 0-9), dash (-), or
underscore (_). No special character or space is allowed.* </span> 
- **SSID**: Name of the Wi-Fi network you want to connect to.
- **PSK**: Password for the Wi-Fi network.
- **Friendly Name**: Name displayed in HomeBridge.
- **Host**: IP address of the MQTT Broker.
- **User:** MQTT username you set up.
- **Password:** MQTT password you set up.
4. Click Save & Reboot to save the settings and connect.

*If the module does not connect or continues to broadcast the Wi-Fi AP, it means it could not connect to the Wi-Fi network.*

![ap-screenshot](../img/setup-fields-en.png ':size=100%')

### 3. Install [ homebridge-mqttthing](https://github.com/arachnetech/homebridge-mqttthing/tree/master) Plugin
1. Install the Homebridge Mqttthing plugin.
2. Open the Mqttthing plugin settings and select **JSON Config**.
   
   ![hb-1](../img/homebridge-conf-1.png ':size=70%')

3. Add a new config and update the configuration below to match your system.

![hb-2](../img/homebridge-conf-2.png ':size=70%')

For the MQTT Topic, use `mitsubishi2mqtt` for Mitsubishi or `daikin2mqtt` for Daikin.

[LABEL](https://gist.githubusercontent.com/maxmacstn/dd6bdd1bbb0d34435badf2838293997a/raw/config.json ':include :type=code')

4. Click Save.
5. Test control from HomeKit.


