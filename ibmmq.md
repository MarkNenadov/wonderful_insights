IBM MQ insights
===============

amqsget and amqsput (scripts for sending/receiving messages from the console)
---------------------------------------------------------------------------------
* Install ibmmq-samples_9.0.2.0_amd64.deb (for Ubuntu)
* Send message: amqsput QUEUE_NAME CHANNEL_NAME
* Receive message: amqsget QUEUE_NAME CHANNEL_NAME

Dumping a Queue to a file
-------------------------

```dmpmqmsg -m MQTBCT -i TEST_QUEUE -f \tmp\myfile.txt```

Dumping MQ Config to a file
---------------------------

```dmpmqcfg > config.mqsc```

Resources
---------

* MQ Docker Image: https://github.com/ibm-messaging/mq-docker
