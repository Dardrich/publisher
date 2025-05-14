a. How much data your publisher program will send to the message broker in one run?
The publisher program sends 5 messages to the message broker in a run

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Same message broker (both connect to the same RabbitMQ instance running on localhost:5672), same credentials (both use the default guest:guest account), and same communication channel (messages published to the `user_created` queue are consumed by the subscriber from the same queue).

Running RabbitMQ as message broker
![img](publisher/rabbit1.jpg)

