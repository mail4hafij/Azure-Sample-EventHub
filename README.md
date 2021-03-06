# Azure-EventHub
The idea is to emit custom events to an EventHub and receive those events from a consumer group. There are two console projects (EventEmitter, EventReceiver) in this solution. A blob storage account is required to read events from EventHub so that Azure SDK can save checkpoint information in a blob storage. A checkpoint is a index that keeps track of how many events that are read from a eventHub queue.

Fill in the neccessary information in *EventEmitter/Program.cs* 
```
private const string ConnectionString = "your_event_hub_connection_string";
private const string EventHubName = "your_event_hub_name";
```

Fill in the necessary information in *EventReceiver/Program.cs*
```
private const string ConnectionString = "your_event_hub_connection_string";
private const string EventHubName = "your_event_hub_name";
private const string StorageAccountConnectionString = "your_storage_account_connection_string";
private const string BlobContainerName = "your_blob_container_name";
```
## Conceptual model
<img src="Architecture.jpg" />

There are other events streaming solutions in azure. Checkout Azure ServiceBus (https://github.com/mail4hafij/Azure-ServiceBus) or Azure EventGrid (https://github.com/mail4hafij/Azure-EventGrid). You can also use RabbitMQ message queue and orchestrate in kubernetes. Checkout the repo here https://github.com/mail4hafij/rabbit_event_stream.
