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

![MQTT Broker](https://github.com/keepinmindsh/lines_infra/blob/main/mqtt_broker/mqtt_broker.png)

- Publisher는 Topic을 발행하고, Subscriber는 Topic에 구독합니다. Broker는 이들을 중계하는 역할을 하며, 단일 Topic에 여러 Subscriber가 구독할 수 있기 때문에, 1:N 통신 구축에도 유용합니다. 
  - MQTT에서 Topic는 /를 사용해서 구성되기 때문에, 계층에 따라 구성하면 IOT 센서와 같은 데이터를 관리하기에 매우 용이합니다. 

#### MQTT - QOS ( Quality of Service )

- 0 : 메세지는 한번만 전달되며, 전달 이후의 수신 과정을 체크하지 않는다. 
- 1 : 메세지는 한번 이상 전달되고, 핸드세이킹 과정을 추적하나, 엄격하게 추적하지 않기 때문에 중복 수신의 가능서잉 있다. 
- 2 : 메세지는 한번만 전달되고, 핸드세이킹의 모든 과정을 체크한다. 

#### MQTT 브로커 구동하기 

- Mosquitto 
- Hive MQ 
- mosca 
- ActiveMQ 
- RabbitMQ ( Plug-in 형태로 지원 )

```shell
mkdir config &&
mkdir data &&
mkdir log
```

```shell
$ docker run -it -p 1883:1883 -p 9001:9001 -v mosquitto.conf:/Users/lines/sources/samples/mosquitto/config/mosquitto.conf eclipse-mosquitto
```

```shell
persistence true
persistence_location /Users/lines/sources/samples/mosquitto/data/
log_dest file /Users/lines/sources/samples/mosquitto/log/mosquitto.log
```

```shell
 docker run -it -p 1883:1883 -p 9001:9001 -v mosquitto.conf:/Users/lines/sources/samples/mosquitto/config/mosquitto.conf -v /Users/lines/sources/samples/mosquitto/data -v /Users/lines/sources/samples/mosquitto/log eclipse-mosquitto
```


> [MQTT Broker Sample](https://underflow101.tistory.com/29)   
> [MQTT Broker Sample - How to use it](https://levelup.gitconnected.com/how-to-use-mqtt-with-go-89c617915774)     