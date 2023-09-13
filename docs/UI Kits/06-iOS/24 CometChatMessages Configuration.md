You can modify the `CometChatMessages` component's properties using the `CometChatMessagesConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `CometChatMessagesConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(messageHeaderConfiguration: MessageHeaderConfiguration)` | Modify the corner radius of the avatar | 
| `set(messageListConfiguration: MessageListConfiguration)` | Modify the border width of the avatar | 
| `set(messageComposerConfiguration: MessageComposerConfiguration)` | Modify the outer width of the avatar | 
| `set(background: [CGColor]?)` | Modify the border outerView spacing of the avatar | 


---

## Step 1: Create CometChatMessagesConfiguration Object.

```swift
let avatarConfiguration = AvatarConfiguration().set(borderWidth: 2).set(cornerRadius: 15)

let statusIndicatorConfiguration = StatusIndicatorConfiguration().set(cornerRadius: 12).set(borderWidth: 2).set(backgroundColor: .red, forStatus: .offline).set(backgroundColor: .green, forStatus: .online)


let messageReceiptConfiguration = MessageReceiptConfiguration().setDeliveredIcon(icon: UIImage(named: "read-updated.png"))

let messageBubbleConfiguration = MessageBubbleConfiguration()
																.set(messageAlignment: .leftAligned)
																.set(avatarConfiguration: avatarConfiguration)
																.set(messageReceiptConfiguration: messageReceiptConfiguration)

let messageHeaderConfiguration = MessageHeaderConfiguration()
                                 .set(videoCallIcon: UIImage(named: "video-slack.png")
                                 .set(audioCallIcon: UIImage(named: "audio-slack.png")
                                 .hide(info: true)
                                 .set(avatarConfiguration: avatarConfiguration)
                                 .set(statusIndicatorConfiguration: statusIndicatorConfiguration)
                                      
                                      
let textTemplate = CometChatMessageTemplate(defaultTemplate: .text)
let imageTemplate = CometChatMessageTemplate(defaultTemplate: .imageFromGallery)
let documentTemplate = CometChatMessageTemplate(defaultTemplate: .file)

let messageListConfiguration = MessageListConfiguration().setMessageFilter(templates: templates).set(bubbleConfiguration: messageBubbleConfiguration)

let messageComposerConfiguration = MessageComposerConfiguration().set(maxLines: 5).set(cornerRadius: 5)
                                      
let messagesConfigurations = CometChatMessagesConfiguration()
                                      .set(background: [.white])
                                      .set(messageHeaderConfiguration: messageHeaderConfiguration)
                                      .set(messageListConfiguration: messageListConfiguration)
                                      .set(messageComposerConfiguration: messageComposerConfiguration)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [messagesConfigurations])
```

