## Start as service

```
### sas-esp-warehouse.service
[Unit]
Description=IOT demo
Requires=network-online.target
After=network-online.target

[Service]
User=sas
ExecStart=/bin/sh -c '/app/iotdemo/esp/server/objectdetection-server.sh -a 30003 -p 30004 -m /app/iotdemo/astore/DoD_warehouse/yolov2.astore -s /app/iotdemo/astore/DoD_warehouse/schema.txt > /var/log/esp-warehouse.log 2>&1'

[Install]
WantedBy=multi-user.target
```
