## How much data your publisher program will send to the message broker in one run? 
When we kick off the publisher, it sends out five messages in total. Each message is a Borsh-serialized `UserCreatedEventMessage` (just a user ID plus a username) and clocks in at roughly 24 bytes a piece. That means each run pushes about 120 bytes of payload over to the broker.

## The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
Using `amqp://guest:guest@localhost:5672` in both publisher and subscriber simply points them at the same RabbitMQ server running locally (on port 5672) with the default `guest` credentials. In practice, this makes sure anything the publisher emits lands straight into the very queue our subscriber is watching.

## Running RabbitMQ

![alt text](img/image.png)

## Sending and Processing Event

![alt text](img/image2.png)
