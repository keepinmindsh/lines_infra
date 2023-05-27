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

MQTT는 M2M, IOT를 위한 프로토콜로서, 최소한의 전력과 패킷량으로 통신하는 프로토콜입니다. 따라서 IOT와 모바일 어플리케이션 등의 통신에 매주 적합한 프로토콜입니다.  
MQTT는 HTTP, TCP 등의 통신과 같이 클라이언트-서버 구조로 이루어지는 것이 아닌, Broker, Publisher, Subscriber 구조로 이루어집니다.  

![MQTT Broker]()

> [MQTT Broker Sample](https://underflow101.tistory.com/29)   
> [MQTT Broker Sample - How to use it](https://levelup.gitconnected.com/how-to-use-mqtt-with-go-89c617915774)     