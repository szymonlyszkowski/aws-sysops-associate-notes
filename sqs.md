
###### SQS
* Messages stored for max 14 days
* SQS vs Amazon MQ - use MQ when deploying legacy apps. Amazon MQ uses industry standard interfaces so no refactoring needed to app.
* Standard SQS - **ordering messages not guaranteed** (use sequencing information in messages). **At least once ordering**
* SQS FIFO - guarantees messaging ordering. **Exactly once ordering**
* Long pooling - does not return response till message not delivered
* Change queue type -  You must choose the queue type when you create it. However, it is possible to move to a FIFO queue.
* Cost optimize - use batches (request containing batch or single message cost the same).
* `DeleteMessage` - When you issue a DeleteMessage request on a previously-deleted message, Amazon SQS returns a success response.
* `ReceiveMessage` -  SQS returns a message to you, the message stays in the message queue whether or not you actually receive the message. You're responsible for deleting the message
* **visibility timeout** - a period of time during which Amazon SQS prevents other consumers from receiving and processing the message.
 - Default 30 seconds
 - Minimum 0 seconds
 - Maximum 12 hours
