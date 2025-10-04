MQTT
**MQTT (Message Queuing Telemetry Transport)** is a **lightweight, publish-subscribe messaging protocol** designed for low-bandwidth, high-latency, or unreliable networks — perfect for **IoT (Internet of Things)**.

- Works on top of TCP/IP
- Uses a broker to route messages

Broker
The central server that routes messages (e.g., Mosquitto)

Client
Any device/app that connects to the broker (e.g., sensor, Flutter app)

Topic
A string that defines the message channel (e.g., `home/livingroom/temp`)

Publish
A client sends data to a topic

Subscribe
A client listens to messages from a topic


## Message Flow

``` md
[Temperature Sensor] --publishes--> "home/temp" --> [MQTT Broker]
                                 [Subscriber 1] <--
                                 [Subscriber 2] <--

```


## Mosquitto
**Mosquitto** is a lightweight, reliable MQTT broker written in C and widely used for IoT deployments.