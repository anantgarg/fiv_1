You can modify the `CometChatMessageComposer` component's properties using the `MessageComposerConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageComposerConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| setCornerRadius(int radius) | Modify corner radius of the message composer using this configuration | 
| setBorderWidth(int width) | Modify border width of the message composer using this configuration | 
| setTextSize(int size) | Modify text size of the message composer using this configuration | 
| setMaxLines(int numberOfLines) | Modify number of lines of the message composer using this configuration | 
| hideAttachment(boolean isHidden) | Hide attachment icon in the message composer using this configuration | 
| hideMicrophone(boolean isHidden) | Hide microphone in the message composer using this configuration | 
| hideLiveReaction(boolean isHidden) | Hide live reaction button in the message composer using this configuration | 
| hideSendButton(boolean isHidden) | Hide send button in the message composer using this configuration | 


## Step 1: Create MessageComposerConfiguration Object.

```java
MessageComposerConfiguration messageComposerConfig = MessageComposerConfiguration()
  .setMaxLines(5)
  .setCornerRadius(5);
```



## Step 2: Provide it to Configurations in the particular module

```java
setConfiguration(messageComposerConfig);
```

