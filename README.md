# homeassistant-experiabox-v10a
homeassistant-experiaboxv10a
ExperiaBox V10A custom device_tracker component for Home-Assistant.io

Purpose
The purpose of this custom component for Home-Assistant is to track devices that are connected either wired or wirelessly to a Experia Box V10A, including clients connected to the guest network.

Inspired by
This project was inspired by the nmap device_tracker component and the custom components that allows Home-Assistant to track devices connected to the Experia Box V8 and Experia Box V10:

Official Home-Assistant nmap device_tracker
Experia V8 device_tracker by MvdB
Experia V10 device_tracker by kadima-tech
Setup instructions
Copying into custom_components folder
Create a directory custom_components in your Home-Assistant configuration directory. Copy the whole experiaboxv10a folder from this project into the newly created directory custom_components.

The result of your copy action(s) should yield a directory structure like so:

.homeassistant/
|-- custom_components/
|   |-- experiaboxv10a/
|       |-- __init__.py
|       |-- device_tracker.py
|       |-- manifest.json
Enabling the custom_component
In order to enable this custom device_tracker component, add this code snippet to your Home-Assistant configuration.yaml file:

device_tracker:
  - platform: experiaboxv10a
    host: mijnmodem.kpn
    username: admin
    password: PASSWORD
Please use secrets within Home-Assistant to store sensitive data like IPs, usernames and passwords.

Experia Wifi
This device_tracker queries the Experia Box V10A directly. If you are using an Experia Wifi access point in conjunction with your Experia Box V10A, the clients connected to the Experia Wifi access point will also be reported by this device_tracker.

Troubleshooting
I have observed that sometimes the Experiabox V10A times out on the GET /cgi/cgi_clients.js call. What I did to work around this problem is rebooting the Experiabox V10A.
