# Exchanges

A message that has to be delievered to a queue is first sent to an *exchange*. 
The messages sent to an *exchange* are delivered to a *queue* by RabbitMQ based on certain rules known as *routing keys*.

### Routing Keys

A *routing key* is what binds a *queue* to an *exchange*. 

If a message has a *routing key* that does not match any *binding pattern*, then it will be deleted. 

### Types

The AMQP protocol provides the following types of *exchanges*

* *Direct*
* *Fanout*
* *Topic*
* *Headers*


