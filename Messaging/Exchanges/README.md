# Exchanges

A message that has to be delievered to a queue is first sent to an *exchange*. 

### Delivering *messages* to *queues*

The messages sent to an *exchange* are delivered to a *queue* by RabbitMQ based on certain rules known as *routing keys*.

**Routing Keys**

A broker like RabbitMQ routes messages from *exchanges* to *queues* based on *routing keys*.
A *routing key* is what binds a *queue* to an *exchange*. 

**Bindings**

A set of *routing keys* are collectively known as *bindings*.

**Discarded Messages**

If a message has a *routing key* that does not match any *binding pattern*, then it will be deleted. 

**Delivery to Multiple Queues**

RabbitMQ handles the delivery to multiple *queues* based on the *type* of the *exchange* used. 

### Types

The AMQP protocol provides the following types of *exchanges*

* *Direct*
* *Fanout*
* *Topic*
* *Headers*

Each type implements a different routing algorithm for routing messages from *exchanges* to the *queues*. 

### Direct Exchange

With a *direct exchange*, RabbitMQ delivers a *message* to a *queue* if their routing key matches. 

### Fanout Exchange

A *message* sent to a multicast *exchange* is delivered to all the *queues* bound to this *exchange*.

### Topic Exchange

*messages* from different sources can be routed to the same *queue*

### Headers Exchange

With a *headers exchange*, RabbitMQ delivers a *message* to a *queue* by comparing header in the AMQP *message* but not the *routing key*.

It operates identical to the *direct exchange* and performs poorly because of which it does not provide any benefit. 

### Publishing to a *exchange* vs Publishing to a *queue*

If *publishers* send *messages* to a broker's *exchange*, they are decoupled from the *queues* and *consumers* that process the messages. This decoupling allows interesting messaging scenarios to be possible. 

If *publishers* send *messages* directly to a broker's *queue*, they become tightly coupled with the *queues*, which narrows the messaging scanarios that would be possible otherwise.

