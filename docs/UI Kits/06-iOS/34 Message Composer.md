`CometChatMessageComposer` is an independent and important component that allows users to send various types of messages includes text, image, video and custom messages.

It supports the following features:

- ❤️ **Live Reaction -** Allow users to share reaction on their chat.
- ⭐ **Attachments** - Shows BottomSheet to display list of attachments.
- ⌨️ **Typing events** - Handles typing indicator internally.
- ✍️ **Editing messages** - Includes view used to "Edit" or "Reply" to a specific message.
- 🎤 **Voice Notes -** On click of Mic audio recording gets started and once it get finished, user will have option to either send it or delete it.
- ↩️ **Replies** - Allow users to share their reply on any type of messages.

![](https://uploads.developerhub.io/prod/x9W8/cp287iufgehk8lethm6busxtny6p9063gr9lyvrw2ujhl0r1w2s6539pujif3rs4.png)

---

## Components

`CometChatMessageComposer` mainly contains below component:

|  |  |  | 
| ---- | ---- | ---- | 
| CometChatActionSheet | `CometChatActionSheet` is a component which present list of options in a list mode as well as grid mode as per the user's choice | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/action-sheet) | 


---

## Methods

### User

`CometChatMessageComposer` takes SDK's `User` object and manipulates the other components in `CometChatMessageComposer`**.**It is use to send messages to the user.

| Method | Description | 
| ---- | ---- | 
| `set(user: User)` | Sets the User object used in the CometChatMessageComposer for all sub-components. \nIt is use to send messages to the user. | 


```swift
__ syntax for set(user: User)	
messageComposer.set(user: user)
```



---

### Group

`CometChatMessageComposer` takes SDK's Group object and manipulates the other components in `CometChatMessageComposer`**.**It is use to send messages to the group.

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | Sets the Group object used in the `CometChatMessageComposer` for all sub-components. It is use to send messages to the group. | 


```swift
__ syntax for set(group: Group)
messageComposer.set(group: group)
```



---

### Background

The background is a `UIView` which is present in the backdrop for CometChatMessageComposer**`.`** You will be able to modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | This method will set the background color for CometChatMessageComposer, it can take an array of multiple colors for the gradient background. | 


```swift
__ syntax for set(background: [UIColor])
messageComposer.set(background: [UIColor.systemBackground.cgColor])
```



---

### Controller

This method will set the instance of the view controller from which the CometChatMessageComposer is presented.

| Method | Description | 
| ---- | ---- | 
| `set(controller: UIViewController)` | This method will set the instance of the view controller from which the CometChatMessageComposer is presented. | 


```swift
__ syntax for set(controller: UIViewController)
messageComposer.set(controller: self)
```



---

### Set Message Types

This method will set the templates of message types which user wants to send the message in the message list from CometChatMessageComposer. This will take array of message type templates to send designated types of messages mentioned in the templates.

| Method | Description | 
| ---- | ---- | 
| `set(messageTypes: [CometChatMessageTemplate]?)` | This method will set the templates of message types which user wants to send the message in the message list from CometChatMessageComposer. | 


```swift
__ syntax for set(messageTypes: [CometChatMessageTemplate]?)

__ New Template from predefined templates
let textTemplate = CometChatMessageTemplate(defaultTemplate: .text)
let imageTemplate = CometChatMessageTemplate(defaultTemplate: .image)
let fileTemplate = CometChatMessageTemplate(defaultTemplate: .file)
let locationTemplate = CometChatMessageTemplate(defaultTemplate: .location)

messageComposer.set(messageTypes: [textTemplate,imageTemplate,  fileTemplate, locationTemplate])
```



---

### Set Excluded Message Types

This method will remove the message types from the list of available message types in CometChatMessageComposer.

| Method | Description | 
| ---- | ---- | 
| `set(excludeMessageTypes: [CometChatMessageTemplate])` | This method will remove the message types from the list of available message types in CometChatMessageComposer. | 


```swift
__ syntax for set(excludeMessageTypes: [String])
messageComposer.set(excludeMessageTypes: [CometChatMessageTemplate(defaultTemplate: .location), CometChatMessageTemplate(defaultTemplate: .poll)])
```



---

### Set MaxLines

This method will specify number of lines in the textview is going to increase in CometChatMessageComposer.

| Method | Description | 
| ---- | ---- | 
| set(maxLines: Int) | This method will specifty number of lines in the textview is going to increase in CometChatMessageComposer. | 


```swift
__ syntax for set(maxLines: Int)
messageComposer.set(maxLines: 5)
```



---

### Set Placeholder

This method will specify placeholder of the textview  in CometChatMessageComposer.

| Method | Description | 
| ---- | ---- | 
| set(placeholderText: String) | This method will specify text of the placeholder  in CometChatMessageComposer. | 
| set(placeholderFont: UIFont) | This method will specify font of the placeholder  in CometChatMessageComposer. | 
| set(placeholderColor: UIColor) | This method will specify color of the placeholder  in CometChatMessageComposer. | 


```swift
__ syntax for set(placeholderText: String)
messageComposer.set(placeholderText: "Type a Message")

__ syntax for set(placeholderFont: UIFont)
messageComposer.set(placeholderFont: UIFont.systemFont(ofSize: 18, weight: .semibold))

__ syntax for set(placeholderColor: UIColor)
messageComposer.set(placeholderColor: .red)
```



---

### Enable Typing Indicator

This method will specify the allowance to send the typing while user is typing in the textview while sending text message in CometChatMessageComposer.

| Method | Description | 
| ---- | ---- | 
| `enable(typingIndicator: Bool)` | This method will specify the allowance to send the typing while user is typing in the textview while sending text message in CometChatMessageComposer. | 


```swift
__ syntax for enable(typingIndicator: Bool)
messageList.enable(typingIndicator: true)
```



---

### Attachment

Attachment button is the UIButton which triggers action sheet from CometChatMessageComposer. You can modify the properties of  button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(attachmentIcon: UIImage)` | Sets the icon for the attachment button in  `CometChatMessageComposer` | 
| `set(attachmentIconTint: UIColor)` | Sets the tint color for the attachment button in `CometChatMessageComposer` | 
| `hide(attachment: Bool)` | Hides the attachment button in `CometChatMessageComposer` | 


```swift
__ syntax for set(attachmentIcon: UIImage) 
messageComposer.set(attachmentIcon: UIImage(named: "attachment.png") 

__ syntax for set(attachmentIconTint: UIColor)
messageComposer.set(attachmentIconTint: .white)

__ syntax for hide(attachment: Bool)
messageComposer.hide(attachment: true)
```



---

### Sticker

Sticker button is the UIButton which triggers sticker keyboard from CometChatMessageComposer. You can modify the properties of button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(stickerIcon: UIImage)` | Sets the icon for the sticker button in  `CometChatMessageComposer` | 
| `set(stickerIconTint: UIColor)` | Sets the tint color for the sticker button in `CometChatMessageComposer` | 
| `hide(sticker: Bool)` | Hides the sticker button in `CometChatMessageComposer` | 


```swift
__ syntax for set(stickerIcon: UIImage) 
messageComposer.set(stickerIcon: UIImage(named: "sticker.png") 

__ syntax for set(stickerIconTint: UIColor)
messageComposer.set(stickerIconTint: .white)

__ syntax for hide(sticker: Bool)
messageComposer.hide(sticker: true)
```



---

### Live Reaction

Live reaction button is the UIButton which triggers live reactions from CometChatMessageComposer. You can modify the properties of button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(liveReactionIcon: UIImage)` | Sets the icon for the live reaction button in  `CometChatMessageComposer` | 
| `set(liveReactionIconTint: UIColor)` | Sets the tint color for the  live reaction button in `CometChatMessageComposer` | 
| `hide(liveReaction: Bool)` | Hides the  live reaction button in `CometChatMessageComposer` | 


```swift
__ syntax for set(liveReactionIcon: UIImage) 
messageComposer.set(liveReactionIcon: UIImage(named: "live-reaction.png") 

__ syntax for set(liveReactionIconTint: UIColor)
messageComposer.set(liveReactionIconTint: .white)

__ syntax for hide(liveReaction: Bool)
messageComposer.hide(liveReaction: true)
```



---

### Send

Send button is the UIButton which sends text messages from CometChatMessageComposer. You can modify the properties of button using below methods:

| Methods | Description | 
| ---- | ---- | 
| `set(sendIcon: UIImage)` | Sets the icon for the send button in  `CometChatMessageComposer` | 
| `set(sendIconTint: UIColor)` | Sets the tint color for the send button in `CometChatMessageComposer` | 
| `show(sendButton: Bool)` | shows the  send button in `CometChatMessageComposer` | 


```swift
__ syntax for set(sendIcon: UIImage) 
messageComposer.set(sendIcon: UIImage(named: "send.png") 

__ syntax for set(sendIconTint: UIColor)
messageComposer.set(sendIconTint: .white)

__ syntax for hide(sendButton: Bool)
messageComposer.show(sendButton: true)
```



### Hide Composer

This method will hide/show the CometChatMessageComposer 

| Method | Description | 
| ---- | ---- | 
| `hide(messageComposer: Bool)` | This method will hide/show the CometChatMessageComposer | 


```swift
__ syntax for hide(messageComposer: Bool)
messageComposer.hide(messageComposer: false)
```



---

### Close

close button is the UIButton which present in the message preview window in  CometChatMessageComposer. By clicking on the close button it will close the message preview window from the composer. You can modify the properties of button using below methods:

|  |  | 
| ---- | ---- | 
| `set(closeButtonIcon: UIImage)` | Sets the icon for the close button in `CometChatMessageComposer` | 
| `set(closeButtonTint: UIColor)` | Sets the tint color for the close button in `CometChatMessageComposer` | 


```swift
__ syntax for set(closeButtonIcon: UIImage) 
messageComposer.set(closeButtonIcon: UIImage(named: "close.png") 

__ syntax for set(closeButtonTint: UIColor)
messageComposer.set(closeButtonTint: .white)
```



---

### Title

The title is a `UILabel` which specifies a title in the message preview window for CometChatMessageComposer. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(title: String)` | Sets the title in message preview for CometChatMessageComposer. | 
| `set(titleWithAttributedText: NSAttributedString)` | Sets the title with attributed text  in message preview for CometChatMessageComposer. | 
| `set(titleColor: UIColor)` | Sets the title color  in message preview for CometChatMessageComposer. | 
| `set(titleFont: UIFont)` | Sets the title font  in message preview for CometChatMessageComposer. | 


```swift
__ syntax for set(title: String)
messageComposer.set(title: "Edit Message")

__ syntax for set(titleColor: UIColor)
messageComposer.set(titleColor: UIColor.black)

__ syntax for set(titleFont: UIFont)
messageComposer.set(titleFont: UIFont.systemFont(ofSize: 22, weight: .medium))
```



---

### Subtitle

The subTitle is a `UILabel` which specifies a subTitle in the message preview window for CometChatMessageComposer. You can modify the title using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(subTitle: String)\n\n` | Sets the subTitle in message preview for CometChatMessageComposer. | 
| `set(subTitleWithAttributedText: NSAttributedString)\n\n` | Sets the subTitle with attributed text  in message preview for CometChatMessageComposer. | 
| `set(subTitleColor: UIColor)\n\n` | Sets the subTitle color  in message preview for CometChatMessageComposer. | 
| `set(subTitleFont: UIFont)\n\n` | Sets the subTitle font  in message preview for CometChatMessageComposer. | 


```swift
__ syntax for set(title: String)
messageComposer.set(title: "you are mine")

__ syntax for set(titleColor: UIColor)
messageComposer.set(titleColor: UIColor.white)

__ syntax for set(titleFont: UIFont)
messageComposer.set(titleFont: UIFont.systemFont(ofSize: 18, weight: .medium))
```



---

### Show message preview

This method will enable the message preview for the functionality such as edit message or reply message. This takes the enum  MessageComposerMode which has two states such as: 

1. Edit 
2. Reply

|  |  | 
| ---- | ---- | 
| `preview(message: BaseMessage, mode: MessageComposerMode)` | This method will enable the message preview for the functionality such as edit message or reply message.`MessageComposerMode` which has two states such as: \n\n`.edit, .reply` | 


```swift
__ syntax for preview(message: BaseMessage, mode: MessageComposerMode)
messageComposer.preview(message: message, mode: .edit)
```



---

### Sound

This method will enable the message sending sound and modify the behaviour of it's own.

|  |  | 
| ---- | ---- | 
| `enable(soundForMessages: Bool)` | This method will enable the message sending sound in CometChatMessageComposer | 


```swift
__ syntax for enable(soundForMessages: Bool)
messageComposer.enable(soundForMessages: true)
```



---

### Set Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

| Method | Description | 
| ---- | ---- | 
| `set(configurations: [CometChatConfiguration]?)` | This method will take the array of configurations and then internally it will process configurations for the required components | 


```swift
__ creating object of MessageComposerConfiguration
let messageComposerConfiguration =  MessageComposerConfiguration().set(maxLines: 3)
                                 .set(placeholderText: "Enter new message")


messageComposer.set(configurations: [messageComposerConfiguration])
```

