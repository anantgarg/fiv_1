You can modify the MessageList component's properties using the MessageListConfiguration object. To use a configuration, you simply need to pass it to the parent component.

The MessageListConfiguration supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| set(limit: Int) | This method will specify the option to set the limit to fetch messages | 
| show(onlyUnreadMessages: Bool) | This method will specify the option to show only unread messages while fetching the messages | 
| hide(messagesFromBlockedUsers: Bool) | This method will specify the option to hide messages from the blocked users while fetching the messages | 
| hide(deletedMessages: Bool) | This method will specify the option to hide deleted messages while fetching the messages | 
| hide(threadedReplies: Bool) | This method will specify the option to hide threaded replies while fetching the messages | 
| hide(error: Bool) | This method will hide the error message popup when the interruption happens | 
| set(tags: [String]) | This method will specify the option to filter the messages using tags | 
| set(messageTypes: [CometChatMessageTemplate]) | This method will set the templates of message types which user wants to display in the message list. This will take array of message type templates to show designated types. | 
| set(excludeMessageTypes: [String]) | This method will remove the message types from the list of available message types | 
| set(emptyText: String) | This method will add the message to be displayed on the UI when the messages are empty | 
| set(errorText: String) | This method will add the message to be displayed on the UI when user faces any interruption while fetching message | 
| scrollToBottomOnNewMessage(bool: Bool) | This option will scroll the message list to the bottom whenever user receives new message. | 
| showEmojiInLargerSize(bool: Bool) | This method specifies the option to show the emojis in large sizes in Text Message bubble | 
| set(messageBubbleConfiguration: MessageBubbleConfiguration) | This method specifies the option to provide configurations to  Message bubbles | 
| set(excludedMessageOptions: [CometChatMessageOption]) | This method will remove the message options from the list of available message options | 
| set(messageAlignment: MessageAlignment) | This method specifies the alignment of the message list as per user choice. | 
| set(messageBubbleTimeAlignment: MessageBubbleTimeAlignment) | This method specifies the alignment of the time message bubble as per user choice. | 
| enableSoundForMessages(bool: Bool) | This method will enable the sounds for the messages. | 


---

## How to create MessageListConfiguration Object and use it ?

#### please refer the below code snippet to create the object of MessageListConfiguration and configure it

```swift
let messageListConfiguration = MessageListConfiguration()

let textTemplate = CometChatMessageTemplate(defaultTemplate: .text)
let imageTemplate = CometChatMessageTemplate(defaultTemplate: .image)
let fileTemplate = CometChatMessageTemplate(defaultTemplate: .file)
let locationTemplate = CometChatMessageTemplate(defaultTemplate: .location)


messageListConfiguration.set(limit: 10)
.show(onlyUnreadMessages: true)
.hide(messagesFromBlockedUsers: true)
.hide(deletedMessages: true)
.hide(threadedReplies: true)
.hide(error: Botrueol)
.set(tags: ["abc"])
.set(messageTypes: [textTemplate, imageTemplate, fileTemplate, locationTemplate])
.set(emptyText: "No Messages")
.set(errorText: "Unable to fetch messages at this moment")
.scrollToBottomOnNewMessage(bool: true)
.showEmojiInLargerSize(bool: true)
.set(messageAlignment: .standard)
.enableSoundForMessages(bool: true)
```



## Usage

MessageListConfiguration can be use in a module where CometChatMessageList is present as an child component. we can easily set MessageListConfiguration object to the parent component by calling setConfiguration method.

```swift
self.set(configurations: [messageListConfiguration])
```

