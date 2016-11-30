# Use Case

A service in an app has to keep track of seat bookings for registered members for a conference

The service has to handle the following tasks

1. Store the member ID and their reserved seat number 
2. Given a member ID, return the associated seat number reserved

*Task 1*

The service can be designed to be a

* *consumer*: to receive a *message*, "Save Member", with the payload that contains the member ID and the seat number reserved.

*Task 2*

The service can be designed to be a

* *consumer*: to receive a *message*, "Get Seat Number", with the payload that contains a member ID and 
* *producer*: to respond with a *message* that contains the seat number of the member ID requested

### Block Diagram

![](_misc/Block%20Diagram.png)

The service can be implemented to perform the following tasks

1. **Open a connection**: Open a TCP connection to the RabbitMQ broker
2. **Create a thread**: Create a consumer thread that can consume and process *messages* from RabbitMQ
3. **Create a Channel**: Create a *channel* named "channel_receive" so that the thread of the service that acts as a *consumer* can
  * Subscribe to a *queue* over a *channel*
  * Receive *messages* from the *queue* subscribe to
4. **Subscribe to a queue**: Subscribe to the *queue* that receives "Save Member" and "Get Seat Number" messages. The subscription to the *queue* is done over the channel "channel_receive".
5. **Store Information**: When the service receives a "Save Member" message over the channel "channel_receive", it should retrieve the data, member ID and seat number, from the message and save it to a database.
6. **Look up**: When the service receives a "Get Seat Number" message over the channel "channel_receive", it should look up the seat number for a given member ID 
7. **Create a thread**: Create a thread per a "Get Seat Number" *message* to respond to the *message*. The number of threads to be created depends on the number of "Get Seat Number" *messages* received at that point in time.
8. **Create a Channel**: Each thread responding to a "Get Seat Number" *message* creates a *channel* named "channel_send_X" to send the response over. X stands for the thread number that would be sending the response over the *channel*
9. **Sending a response**: Each thread responding to a "Get Seat Number" *message*, retrieves the seat number of a given member ID and creates the response *message*, which includes label and payload, and publishes it to RabbitMQ over the *channel* "channel_send_X"

