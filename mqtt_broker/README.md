# MQTT Broker and Setting 

```shell 
$ docker pull eclipse-mosquitto

$ docker run -it -d --name mos1 -p 1883:1883 -p 9001:9001 -v /Users/lines/sources/samples/mosquitto/mosquitto.conf:/mosquitto/config/mosquitto.conf eclipse-mosquitto
```

> [https://hub.docker.com/_/eclipse-mosquitto](https://hub.docker.com/_/eclipse-mosquitto)   
> [https://cedalo.com/blog/mosquitto-docker-configuration-ultimate-guide/](https://cedalo.com/blog/mosquitto-docker-configuration-ultimate-guide/)

## MQTT Explorer 

- [MQTT Explorer](https://mqtt-explorer.com/)


### MQTT Broker Sample 

- 주의할 점은, mqtt_server에 적는 IP Address는 127.0.0.1이나 localhost가 아닌, 실제 PC의 IP Address여야 한다. 

> [MQTT Broker Sample](https://underflow101.tistory.com/29)   
> [MQTT Broker Sample - How to use it](https://levelup.gitconnected.com/how-to-use-mqtt-with-go-89c617915774)     