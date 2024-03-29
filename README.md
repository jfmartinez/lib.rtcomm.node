#lib.rtcomm.node

This repository contains the 'rtcomm' node.js Module. This module extends the real-time communications services of the WebSphere Liberty profile. Currently, the service extensions represented in 
this library include :

1. RtcConnector: Provides the ability to monitor all events related to the rtcomm protocol including session and presence events. 
2. 3PCC (Third party call control):  Providers the ability to initiate a 3rd party calls.

This module relies on both a message broker for sending (publishing) and receiving messages and the WebSphere Liberty rtcomm-1.0 feature to deliver these services. This node.js module is simply a client to these services. It can subscribe and receive RtcConnector related events and it can initiate a 3rd party call between two endpoints 
that are both registered with the WebSphere Liberty server. 

##Install
```
npm install rtcomm

Note: specific releases of this repository can be installed via the following command:
npm install rtcomm@<version>

See the wiki page for what versions have been tested with specific versions of the 
WebSphere Liberty profile.
```

This module relies on the following:

1. An MQTT broker for publishing and receiving messages. 
2. An Rtcomm server that supports Rtcomm 3rd party calling and/or event monitoring. 

**MQTT Broker examples:**

There are many MQTT brokers on the market, both publicaly accessible and 

Because Liberty does not currently include native support for an MQTT message broker, this feature requires an external broker. Many options of MQTT message brokers exist in the market today. Here is a list of some of the more commonly used MQTT message brokers:

[IBM MessageSight](http://www-03.ibm.com/software/products/en/messagesight)  
[WebSphere MQ Telemetry](http://www-03.ibm.com/software/products/en/wmq-telemetry)  
[Mosquitto](http://mosquitto.org/) (open source MQTT broker)  

A quick options for demonstrations and testing this module is tcp://broker.mqttdashboard.com:1883. 
The MQTT Dashboard is an open, publicly accessible MQTT broker.  

**Rtcomm server example:**

The WebSphere Liberty profile beta extended package which can be downloaded from: 
https://developer.ibm.com/wasdev/downloads/liberty-profile-beta/

##Documentation

There are three parts to the documentation of this module:

1. The Rtcomm services protocol that is implemented by this module: [rtcomm.service.proto.spec.md](/rtcomm.service.proto.spec.md)
2. The API specification for this module: [rtcomm.service.api.spec.md](/rtcomm.service.api.spec.md)
3. The Presence events are defined on: [rtcomm.signaling.proto.md](https://github.com/WASdev/lib.rtcomm.clientjs/blob/master/rtcomm.signaling.proto.spec.md)

##Testing

This module relies on Mocha for testing and utilizes the Mosca MQTT broker. Instructions for running the test:

1. From the root rtcomm-node director type: npm install
2. Run mocha: ./node_modules/.bin/mocha

