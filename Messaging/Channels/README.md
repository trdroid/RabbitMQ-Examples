# Channels

*Channels* allow an application for the creation of as many transport layers as required by overcoming the TCP connection restrictions.

A *Channel* is a virtual connection inside a TCP connection over which the AMQP commands are issued. 
A few of the AMQP commands include commands to perform the following tasks, which are performed over *channels*

* Publishing a *message* 
* Receiving a *message*
* Subscribing to a *queue*

### Publishing and Consuming *messages* over *channels*

*Producers* publish *messages* to RabbitMQ over *channels*

*Consumers* consume *messages* to RabbitMQ over *channels*

![](_misc/Channels%20Block%20Diagram.png)


### AMQP commands over TCP vs AMQP commands over Channels

Setting up and tearing down TCP sessions is expensive for an operating system. 
There is a limit on the number of TCP

