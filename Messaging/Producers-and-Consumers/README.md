# Producers

*Producers* create messages and publish them to a RabbitMQ broker server. 

Creating messages involve creating the payload and labelling them for routing

### Message

A message contains two parts

* a Label
* a Payload

# Consumer

*Consumers* attach to the RabbitMQ broker server and subscribe to a queue. 

A queue can be considered to be a named mailbox.


# Connecting to RabbitMQ

For a producer to publish a message to RabbitMQ or for a consumer to consume a message from RabbitMQ, they should

1. Connect to the RabbitMQ broker server by creating a TCP connection to it
2. Authenticate with RabbitMQ broker server
3. Create an AMQP channel
