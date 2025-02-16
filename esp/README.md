# Start ESP server

# How run models
## Premise
```
nohup /app/iotdemo/esp/server/objectdetection-server.sh -a 30001 -p 30002 -m /app/iotdemo/astore/DoD_Premise/yolov2.astore -s /app/iotdemo/astore/DoD_Premise/schema.txt > /app/logs/esp-premise.log 2>&1 &
```

## Warehouse
```
nohup /app/iotdemo/esp/server/objectdetection-server.sh -a 30003 -p 30004 -m /app/iotdemo/astore/DoD_warehouse/yolov2.astore -s /app/iotdemo/astore/DoD_warehouse/schema.txt > /app/logs/esp-warehouse.log 2>&1 &

bash /app/iotdemo/esp/server/objectdetection-server.sh -a 30003 -p 30004 -m /app/iotdemo/astore/DoD_warehouse/yolov2.astore -s /app/iotdemo/astore/DoD_warehouse/schema.txt -d
```

## Drone WebCam
```
nohup /app/iotdemo/esp/server/objectdetection-server.sh -a 30005 -p 30006 -m /app/iotdemo/astore/DoD_DroneWebcam/yolov2.astore -s /app/iotdemo/astore/DoD_DroneWebcam/schema.txt > /app/logs/esp-dronewebcam.log 2>&1 &
```
##
```
sudo cp /app/iotdemo/esp/server/services/sas-esp-dronewebcam.service /etc/systemd/system/sas-esp-dronewebcam.service
sudo chmod 644 /etc/systemd/system/sas-esp-dronewebcam.service
sudo systemctl start sas-esp-dronewebcam
sudo systemctl daemon-reload
```

```
nohup /app/iotdemo/esp/server/objectdetection-server.sh -a 30001 -p 30002 -m /app/iotdemo/astore/Yolov2_OutOfBox/Tiny-Yolov2 -s /app/iotdemo/astore/Yolov2_OutOfBox/schema.txt > /app/logs/esp-default-yolov2.log 2>&1 &
```
# Start client

## Stream

### Premise
```
python client/stream/premise.py
```

### Warehouse
```
python client/stream/warehouse.py
```

### Drone WebCam
```
python client/stream/dronwebcam.py
```
