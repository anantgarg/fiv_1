Messages that are started from a particular message are called Threaded messages or simply threads.
Each Thread is attached to a message which is the Parent message for that thread.

## Send Message in a Thread

As mentioned in the [Send a Message](https://www.cometchat.com/docs/v3/android-chat-sdk/messaging-send-message) section, you can send a message to a User or a Group by mentioning the receiver (uid/guid) and  `receiverType`(user/group).

A message can be categorized as:

1. Text Message
2. Media Message
3. Custom Message.

Any of the above messages can be sent in a thread. As a thread is identified with a parent message, the `parentMessageId` must be set for the message. This will indicate that the message to be sent has to be a part of the thread of the message with the specified `parentMessageId`.

This can be achieved using the `setParentMessageId()` method provided by the object of the `TextMessage`, `MediaMessage` and `CustomMessage` class. The id specified in the `setParentMessageId()` method maps the message sent to the particular thread.

**Example to Send a Text Message in a thread in a user conversation.**

```java
TextMessage textMessage = new TextMessage(UID, "Hello", CometChatConstants.RECEIVER_TYPE_USER);
textMessage.setParentMessageId(100);

CometChat.sendMessage(textMessage, new CometChat.CallbackListener<TextMessage>() {
  @Override
    public void onSuccess(TextMessage textMessage) {
		Log.d(TAG, "Text Message Sent successfully");
  }

  @Override
    public void onError(CometChatException e) {
    Log.d(TAG, "Text Message Failed : " + e.getMessage());
  }
});
```

```kotlin
val textMessage = TextMessage(UID, "Hello", CometChatConstants.RECEIVER_TYPE_USER)
textMessage.parentMessageId = 100

CometChat.sendMessage(textMessage, object : CallbackListener<TextMessage?>() {
  override fun onSuccess(textMessage: TextMessage?) {
    Log.d(TAG, "Text Message Sent successfully")
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "Text Message Failed : " + e.message)
  }
})
```



The above snippet shows how a message with the text "Hello" can be sent in the thread with `parentMessageId` 100.

Similarly, using the `setparentMessageId()` method, Media and Custom Messages can be sent in threads too.

### Receiving Real-Time Messages

The procedure to receive real-time messages is exactly the same as mentioned in the [Receive Messages](https://www.cometchat.com/docs/v3/android-chat-sdk/messaging-receive-messages). This can be achieved using the `MessageListener` class provided by the SDK.
To add a MessageListener, you can use the `addMessageListener()` method of the SDK.
The only thing that needs to be checked is if the received message belongs to the active thread. This can be done using `parentMessageId` field of the message object.

```java
private String listenerID = "UNIQUE_LISTENER_ID";
private int activeThreadId = 100;

CometChat.addMessageListener(listenerID, new CometChat.MessageListener() {
  @Override
  public void onTextMessageReceived(TextMessage textMessage) {
    if(message.getParentMessageId() == activeThreadId) {
    	Log.d(TAG,"Text Message Received for active thread");
    }
  }
  @Override
  public void onMediaMessageReceived(MediaMessage mediaMessage) {
    if(message.getParentMessageId() == activeThreadId) {
    	Log.d(TAG,"Media Message Received for active thread");
    }
  }
@Override
  public void onCustomMessageReceived(CustomMessage customMessage) {
	if(message.getParentMessageId() == activeThreadId) {
    	Log.d(TAG,"Custome Message Received for active thread");
  }
}
});
```

```kotlin
val listenerID = "UNIQUE_LISTENER_ID"
val activeThreadId = 100

CometChat.addMessageListener(listenerID, object : MessageListener() {
    override fun onTextMessageReceived(textMessage: TextMessage) {
        if (message!!.parentMessageId === activeThreadId) {
            Log.d(TAG, "Text Message Received for active thread")
        }
    }

    override fun onMediaMessageReceived(mediaMessage: MediaMessage) {
        if (message!!.parentMessageId === activeThreadId) {
            Log.d(TAG, "Media Message Received for active thread")
        }
    }

    override fun onCustomMessageReceived(customMessage: CustomMessage) {
        if (message!!.parentMessageId === activeThreadId) {
            Log.d(TAG, "Custome Message Received for active thread")
        }
    }
})
```



### Fetch all the messages for any particular thread.

You can fetch all the messages belonging to a particular thread by using the `MessagesRequest` class.

The `MessageRequestBuilder` builds the `MessageRequest` object using the following functions:

1. setParentMessageId(): Takes the parentId of the message as argument whose thread needs to be requested.
2. build(): returns the MessageRequest object.

Once you have the  `MessagesRequest` object, you can call the `fetchPrevious()` method to get the latest messages in the thread. In one iteration, a maximum of 100 messages can be fetched. If you wish to fetch the next set of messages, you need to call the fetchPrevious() method again on the same object.

```java
MessagesRequest messagesRequest = neMessagesRequest.MessagesRequestBuilder()
  .setLimit(30)
  .setParentMessageId(100)
  .build();
       
messagesRequest.fetchPrevious(new CometChat.CallbackListener<List<BaseMessage>>() {
  @Override
    public void onSuccess(List<BaseMessage> messages) {
    Log.d(TAG, "Messages for thread fetched successfully");        
  }

  @Override
    public void onError(CometChatException e) {
    Log.d(TAG, "Message Fetching failed : "+ e.getMessage());
  }
});
```

```kotlin
val messagesRequest: MessagesRequest = neMessagesRequest.MessagesRequestBuilder()
  .setLimit(30)
  .setParentMessageId(100)
  .build()

messagesRequest.fetchPrevious(object : CallbackListener<List<BaseMessage?>?>() {
  override fun onSuccess(messages: List<BaseMessage?>?) {
    Log.d(TAG, "Messages for thread fetched successfully")
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "Message Fetching failed : " + e.message)
  }
})
```



## Avoid Threaded Messages in User/Group Conversations

While fetching messages for normal user/group conversations using the `MessagesRequest`, the threaded messages by default will be a part of the list of messages received. In order to exclude the threaded messages from the list of user/group messages, you need to use the `hideReplies()` method of the `MessagesRequestBuilder` class. This method takes a boolean argument which when set to true excludes the messages belonging to threads from the list of messages.

```java
MessagesRequest messagesRequest = neMessagesRequest.MessagesRequestBuilder()
  .setLimit(30)
  .setUID("superhero1")
  .hideReplies(true)
  .build();
       
messagesRequest.fetchPrevious(new CometChat.CallbackListener<List<BaseMessage>>() {
  @Override
    public void onSuccess(List<BaseMessage> messages) {
    Log.d(TAG, "Messages for thread fetched successfully");        
  }

  @Override
    public void onError(CometChatException e) {
    Log.d(TAG, "Message Fetching failed : "+ e.getMessage());
  }
});
```

```kotlin
val messagesRequest: MessagesRequest = neMessagesRequest.MessagesRequestBuilder()
  .setLimit(30)
  .setUID("superhero1")
  .hideReplies(true)
  .build()

messagesRequest.fetchPrevious(object : CallbackListener<List<BaseMessage?>?>() {
  override fun onSuccess(messages: List<BaseMessage?>?) {
    Log.d(TAG, "Messages for thread fetched successfully")
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "Message Fetching failed : " + e.message)
  }
})
```



The above snippet will return messages between the logged in user and `superhero1` excluding all the threaded messages belonging to the same conversation.