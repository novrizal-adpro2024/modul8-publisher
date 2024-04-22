# Module 8: Software Architecture

> #### Novrizal Airsyahputra - 2206081780 - Advance Programming B

---

### Reflection

**a. How many data your publisher program will send to the message broker in one run?**

**ANS:** 
Publisher program will send 5 data to the message broker in one run. I can see that from the code.
```
_ = p.publish_event("user_created".to_owned(),
    UserCreatedEventMessage { user_id: "1".to_owned(), user_name:
    "2206081780-Amir".to_owned() });
_ = p.publish_event("user_created".to_owned(),
    UserCreatedEventMessage { user_id: "2".to_owned(), user_name:
    "2206081780-Budi".to_owned() });
_ = p.publish_event("user_created".to_owned(),
    UserCreatedEventMessage { user_id: "3".to_owned(), user_name:
    "2206081780-Cica".to_owned() });
_ = p.publish_event("user_created".to_owned(),
    UserCreatedEventMessage { user_id: "4".to_owned(), user_name:
    "2206081780-Dira".to_owned() });
_ = p.publish_event("user_created".to_owned(),
    UserCreatedEventMessage { user_id: "5".to_owned(), user_name:
    "2206081780-Emir".to_owned() });
```

**b. The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber
program, what does it mean?**

**ANS:**
If the URL is identical, it indicates that both the publisher and subscriber in the AMQP broker share the same connection. 
Alternatively, it suggests that the publisher and subscriber are linked within the same messaging broker infrastructure.
It also means that the subscriber program is configured to connect to the messaging system using this URL.

- `amqp://`: Indicates the protocol being used (AMQP).
- `guest:guest@`: Default credentials for accessing the messaging system. `guest` is usually the default username and password.
- `localhost`: Refers to the hostname or IP address of the server where the messaging system is running. 
- `5672`: Default port number for AMQP connections.

**c. Running RabbitMQ as message broker.**

![Running RabbitMQ](https://cdn.discordapp.com/attachments/1111642397248598067/1231972806309445693/image.png?ex=6638e715&is=66267215&hm=d86c4c43c7663b85cf121f1a58f874d2d52d4b56e397a6494361085dac462adc&)

**d. Sending and processing event.**

When i tried to run `cargo run` in both directory, these are the outputs that i received:

- Publisher
![Publisher](https://cdn.discordapp.com/attachments/1111642397248598067/1231977535466901585/image.png?ex=6638eb7d&is=6626767d&hm=276152253b0c9e7c02f08f5f52cc1f6e76cd0bbcda1b1bb201421b5f66020782&)

- Subscriber
![Subscriber](https://cdn.discordapp.com/attachments/1111642397248598067/1231977751733342208/image.png?ex=6638ebb1&is=662676b1&hm=becad5d199cf9b1e9c94df51bf7991d36427c5fb32e8aa49215a74042b735744&)

It is clear that when i run the Publisher, it will send 5 events to the message broker (which will be consumed by Subscriber).


**e. Monitoring chart based on publisher.**

![Chart RabbitMQ](https://cdn.discordapp.com/attachments/1111642397248598067/1231978660815306773/image.png?ex=6638ec89&is=66267789&hm=94cd847b340586fead1af750e6a83080806778dfc82ee5f0145218ae3d448e84&)

I set the chart to display for last minutes. 
The graph displaying spikes is the Message Rates graph. 
It illustrates how many messages were sent by the publisher within the last minute. 
The higher the spike, the faster the message rate.