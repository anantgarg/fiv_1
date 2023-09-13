You can modify the `CometChatMessageList` component's properties using the `MessageListConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageListConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| setMessageAlignment(@CometChatMessageList.MessageListAlignment String alignment) | Modify the Message Alignment in Message List. It can be either set to LEFT_ALIGNED or STANDARD. | 
| setDeleteMessageHidden(boolean isHidden) | Used to hide deleted Messages from MessageList. | 


## Step 1: Create MessageListConfiguration Object.

```java
MessageListConfiguration messageListConfiguration=new MessageListConfiguration()
        .setMessageAlignment(CometChatMessageList.STANDARD)
        .setDeleteMessageHidden(false);
```



## Step 2: Provide it to Configurations in the particular module

```java
setConfiguration(messageListConfiguration);
```

