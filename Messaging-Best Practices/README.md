# Messaging Best Practices

**Use Message Acknowledgments**

- Acknowledge after processing: Ensure that you only acknowledge a message after it has been successfully processed. This prevents message loss in case of processing failures.

- Automatic retries: For failed messages, configure automatic retries before moving them to a dead letter queue (DLQ).

