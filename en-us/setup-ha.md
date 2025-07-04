# Adding to Home Assistant
WiFiKit Serial communicates with Home Assistant via the MQTT protocol. Therefore, you need to set up an MQTT Broker and MQTT Integration first. If you have already done this, you can skip ahead to [connecting to Home Assistant](#_2-connect-wifikit-serial-to-home-assistant)

## Installation Video
<iframe style="width:100% ; aspect-ratio: 16 / 9"  src="https://www.youtube.com/embed/uPHk5j-ZJIM?si=KHFE2BC38sMSddzB" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## Installation Steps

### 1. Install MOSQUITTO MQTT Broker
1. Go to Settings -> Add-ons -> Add-on Store -> Mosquitto Broker.
2. Click INSTALL and wait for the installation to complete.
3. Click START.
4. Go back to Settings -> Integration, you should see MQTT appear under Discovered.
5. Click Configure and follow the steps.

<span style="color:red"> By default, the MQTT Username and Password are the same as your Home Assistant credentials. </span> <br> If you want to set them differently, go to the Configuration tab and set the MQTT username and password in the `logins` section as shown below:

```
- username: user
  password: passwd
```

### 2. Connect WiFiKit Serial to Home Assistant
1. Use your phone to search for a Wi-Fi network named HVAC-XXXXX and connect to it.
2. The configuration page should open automatically. If not, go to the URL `8.8.8.8`.
3. Enter your Wi-Fi and MQTT details for connection:
- **Hostname**: Device name in the system <br> <span style="color:red"> *MQTT Hostname should contain only alphanumeric (aA-zZ, 0-9), dash (-), or
underscore (_). No special character or space is allowed.* </span> 
- **SSID**: Name of the Wi-Fi network you want to connect to.
- **PSK**: Password for the Wi-Fi network.
- **Friendly Name**: Name displayed in Home Assistant.
- **Host**: IP address of the MQTT Broker.
- **User:** MQTT username you set up.
- **Password:** MQTT password you set up.
4. Click Save & Reboot to save the settings and connect.
5. The air conditioner will automatically appear in the MQTT Integration.

*If the module does not connect or continues to broadcast the Wi-Fi AP, it means it could not connect to the Wi-Fi network.*

![ap-screenshot](../img/setup-fields-en.png ':size=100%')
