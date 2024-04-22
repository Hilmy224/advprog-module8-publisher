## Tutorial 8 & Questions

1. How many data your publlsher program will send to the message broker in one
run?
+ The publisher program will send five data entries to the message broker in one run. We can see from the main function where the `publish_event` method is called five times. For each call it sends `UserCreatedEventMessage` with `user_id` and `user_name`.
+ Details of  event messages to something like this:
```
User ID: "1", Username: "2206828701-Amir"
User ID: "2", Username: "2206828701-Budi"
User ID: "3", Username: "2206828701-Cica"
User ID: "4", Username: "2206828701-Dira"
User ID: "5", Username: "2206828701-Emir"
```
2. The url of: “`amqp://guest:guest@localhost:5672`” is the same as in the subscriber
program, what does it mean?
+ This means that both the publisher and subscriber programs are connected to the same AMQP (Advanced Message Queuing Protocol) message broker instance. 
+ Both the publisher and subscriber programs are communicating with the AMQP server running on the local machine (localhost) using the default username ("guest") and password ("guest"), and the default port (5672).
+ It establishes a unified communication pathway for data exchange between the publisher and subscriber, enabling seamless interaction within the messaging infrastructure.

## Running RabbitMQ
![alt text](image.png)

## Making it work
+ After the publisher is run, the data hardcoded in the publisher will be sent to the message queue. Then, the subscriber will receive this data from the message queue and display the messages as shown in the attachment below.
![alt text](image-1.png)
+ When cargo run is repeatedly performed on the publisher, there will be an increase in the message rate on RabbitMQ, which is the message queue. This can be seen in a spike indicating an increase in message rates at certain times in the chart shows in the attachement below:
![alt text](image-2.png)