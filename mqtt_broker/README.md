# MQTT Broker and Setting 

```shell 
$ docker pull eclipse-mosquitto

$ docker run -it -d --name mos1 -p 1883:1883 -p 9001:9001 -v /Users/lines/sources/samples/mosquitto/mosquitto.conf:/mosquitto/config/mosquitto.conf eclipse-mosquitto
```