These are just my notes so I can run through without blowing something up and I don't need to constantly remember which websites were where.

Thanks to:

- https://tasmota.github.io/ - Firmware
- http://sonoff-ota.aelius.com/ - OTA Flashing

- Connect to power
    - If connecting to an extension neutral should be the thicker prong
- Configure DIY Mode
    - Hold button (10-20 seconds)
        - Should start flashing constantly
    - Connect to Sonoff mini DIY mode
        - Hotspot `ITEAD-*` wifi hotspot
        - Password: `12345678`
    - Nagivate to http://10.10.7.1/
    - Enter wifi credentials
- Flash with Tasmota
    - Find IP Address (hostname EPS_*)
    - Run `./sonoff-ota-flash.sh -i <ip address>` (http://sonoff-ota.aelius.com/)
    - Press y
    - May take a minute or two to finish
- Configure Sonoff WIFI
    - Connect to Tasmota wifi hotpot
        - `TASMOTA_*`
    - Web browser should automatically redirect
    - Enter wifi credentials
- Configure Sonoff
    - Navigate to ip address from earlier (hostname now `tasmota_*`)
    - Upgrade Firmware
        - Click Firmware Upgrade
        - Click Start upgrade (OTA Url)
    - Load sonoff-mini config
        - Click Configuration
        - Click Configure Other
        - Enter the following Tempate
            ~~~
            {"NAME":"Sonoff Mini","GPIO":[32,0,0,0,160,0,0,0,224,320,0,0,1,0],"FLAG":0,"BASE":1}
            ~~~
        - Enable MQTT
        - Enable WeMo emulation
    - Update hostname
        - Click Configuration
        - Click Configure WiFi
        - Enter Hostname
        - Click Save
