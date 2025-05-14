a. How much data your publisher program will send to the message broker in one run?

The publisher program sends 5 messages to the message broker in a run

b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Same message broker (both connect to the same RabbitMQ instance running on localhost:5672), same credentials (both use the default guest:guest account), and same communication channel (messages published to the `user_created` queue are consumed by the subscriber from the same queue).

### Running RabbitMQ as message broker
![alt text](rabbit1.jpg)

### Sending and processing event
![alt text](rabbit2.jpg)
So, in that screenshot, it generates and publishes 5 events to the message broker by first, the publisher connects to the message broker (appears to be using AMQP protocol), then the publisher generates 5 user creation events, then the publisher sends these events to the message broker, then the subscriber service (running separately) consumes these events, and finally it processes and displays the received events.

### Monitoring chart based on publisher
![alt text](rabbit3.jpg)
Each time the publisher runs, it sends several messages at once to RabbitMQ, causing that sudden jump in the graph. Think of it like a burst of activity that settles back down when the publisher finishes its work.