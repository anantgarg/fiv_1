You can modify the MessageComposer component's properties using the MessageComposerConfiguration object. To use a configuration, you simply need to pass it to the parent component.

The MessageComposerConfiguration supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| set(messageTypes: [CometChatMessageTemplate]) | User can modify corner radius of the message composer using this configuration | 
| set(excludeMessageTypes: [CometChatMessageTemplate]) | User can modify border width of the message composer using this configuration | 
| set(maxLines: Int) | User can modify number of lines of the message composer using this configuration | 
| hide(attachment: Bool) | User can hide attachment icon in the message composer using this configuration | 
| hide(microphone: Bool) | User can hide microphone in the message composer using this configuration | 
| hide(liveReaction: Bool) | User can hide live reaction button  in the message composer using this configuration | 
| hide(sendButton: Bool) | User can hide send button in the message composer using this configuration | 
| hide(sticker: Bool) | User can hide sticker button in the message composer using this configuration | 
| set(placeholderText: String) | User can set placeholder text in the message composer using this configuration | 
| hide(messageComposer: Bool) | User can hide  message composer using this configuration | 
| enable(typingIndicator: Bool) | User can enable typing indicator when the user is typing in the textview in message composer. | 


---

## How to create MessageListConfiguration Object and use it ?

#### please refer the below code snippet to create the object of MessageComposerConfiguration and configure it

```swift
let messageComposerConfiguration = MessageComposerConfiguration()

let textTemplate = CometChatMessageTemplate(defaultTemplate: .text)
let imageTemplate = CometChatMessageTemplate(defaultTemplate: .image)
let fileTemplate = CometChatMessageTemplate(defaultTemplate: .file)
let locationTemplate = CometChatMessageTemplate(defaultTemplate: .location)

messageComposerConfiguration.set(messageTypes: 
                                 [textTemplate,imageTemplate,fileTemplate,  locationTemplate])
                            .set(excludeMessageTypes: [CometChatMessageTemplate(defaultTemplate: .poll])
                            .set(maxLines: 4)
                            .set(placeholderText: "Type a Message")
                            .hide(attachment: false)
                            .hide(sticker: false)
                            .hide(microphone: true)
                            .hide(liveReaction: false)
                            .hide(sendButton: false)
                            .enable(typingIndicator: true)
                            .hide(messageComposer: false)
```



## Usage

MessageComposerConfiguration can be use in a module where CometChatMessageList is present as an child component. we can easily set MessageComposerConfiguration object to the parent component by calling setConfiguration method.

```swift
self.set(configurations: [messageComposerConfiguration])
```

