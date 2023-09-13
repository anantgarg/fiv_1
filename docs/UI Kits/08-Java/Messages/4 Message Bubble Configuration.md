You can modify the `CometChatMessageBubble` component's properties using the `MessageBubbleConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageBubbleConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| setSentMessageInputData(MessageInputData data) | Modify Message bubble of sender side. | 
| setReceiverMessageInputData(MessageInputData data) | Modify Message Bubble of Receiver side. | 
| setMessageReceiptConfiguration(MessageReceiptConfiguration configuration) | Modify the Message Receipt used in Message Bubble | 
| setLeftMessageRadius(float leftMessageRadius) | Modify the Receiver's side Message Bubble radius. | 
| setLeftMessageRadius(float topLeft,float topRight, float bottomLeft, float bottomRight) | Modify the Receiver's side Message Bubble radius. | 
| setRightMessageRadius(float rightMessageRadius) | Modify the Sender's side Message Bubble radius. | 
| setRightMessageRadius(float topLeft,float topRight, float bottomLeft, float bottomRight) | Modify the Sender's side Message Bubble radius. | 
| setAvatarConfiguration(AvatarConfiguration avatarConfiguration) | Modify Avatar component of CometChatMessageBubble using this component | 


## Step 1: Create MessageBubbleConfiguration Object.

```java
__syntax for creating Object of MessageInput Data
MessageInputData messageInputData = new MessageInputData(
                        false, false, false, true, true);

MessageBubbleConfiguration messageBubbleConfig = new MessageBubbleConfiguration()
.setSentMessageInputData(messageInputData)
.setReceiverMessageInputData(messageInputData);
```



## Step 2: Provide it to Configurations in the particular module

```java
setConfiguration(messageBubbleConfig);
```

