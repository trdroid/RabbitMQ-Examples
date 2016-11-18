# Messaging

RabbitMQ focuses on application-to-application messaging. 

### AMQP

**Properties**

The following properties of AMQP allows for a flexible infrastructure that encourages decoupling of applications. 

* *Anonymity*: AMQP keeps the sender and the receiver anonymous from each other by hiding their information
* *Presence*: AMQP has no concept of presence
* *Storage*: AMQP stores messages for consumers who are not online

**Routing**

AMQP messages are routed based on tags which offers flexibility. 

AMQP messages can be routed in the following ways

* Broadcast
  * One-to-many broadcast
  * Selective broadcast
* One-to-One

