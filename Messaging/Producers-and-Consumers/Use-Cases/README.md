# Use Cases

**Case 1**

A service has to keep track of seat bookings for registered members for a conference

The service has to handle the following tasks

1. Store the member ID and their reserved seat number 
2. Given a member ID, return the associated seat number reserved

*Task 1*

The service can be designed to be a 

* *consumer*: to receive a *message*, "Store Member", with the payload that contains the member ID and the seat number reserved.

*Task 2*

The service can be designed to be a 

* *consumer*: to receive a *message*, "Get Seat Number", with the payload that contains a member ID and 
* *producer*: to respond with a *message* that contains the seat number of the member ID requested


The app/service can be implemented to perform the following tasks

1. Open a connection to the RabbitMQ broker
2. Create a *channel* named "channel_receive" for the thread of the app that acts as a *consumer*
3. Subscribe to the *queue* that receives the "Get Seat Number" messages. The subscription to the *queue* is done over the channel "channel_receive".
4. Look up the seat number for a given member ID when the app receives a message over the channel "channel_receive"
5. Create a thread to send the response
6. Create a *channel* named "channel_send_X" to send the response over. X stands for the thread number that would be sending the response over the *channel*
7. Uses the newly created thread to label the response *message* and publishes it to RabbitMQ over the *channel* "channel_send_X"






