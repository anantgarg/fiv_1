## Overview

`CometChatMessageList` is one of the core UI components which displays a list of messages and handles real-time operations. It can contain the following list of possible messages:

- Text messages and Rich Media if text contains URL.
- Attachments (media or file) message.
- Location Sharing
- Collaborative Whiteboard & Document.
- Stickers
- Deleted message (only for current user)
- Sentiment Analysis (e.g. auto blocked message with inappropriate content)
- System message (e.g. some user joined a channel)
- Giphy preview
- Date separator
- Optimistic UI

![](https://uploads.developerhub.io/prod/x9W8/o9cfbiruyfezc2r6jdbaoe12kbpqxs8jv1d2nt4lbatht4q7ha06nwbmadymtr2a.png)

---

## Components

`CometChatMessageList` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatMessageBubble** | `CometChatMessageBubble` and `CometChatTextAutoSizeBubble` are the reusable components which forms different types of message bubbles accordingly. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/message-bubble) | 


---

## Methods

### User

`CometChatMessageList` takes SDK's `User` object and manipulates the other components in `CometChatMessageList`**.**

| Method | Description | 
| ---- | ---- | 
| `set(user: User)` | Sets the User object used in the CometChatMessageList for all sub-components. \nIt fetches the list of messages for this user | 


```swift
__ syntax for set(user: User)	
messageList.set(user: user)	 __ The object which is going to be rendered in the data  item
```



---

### Group

`CometChatMessageList` takes SDK's Group object and manipulates the other components in `CometChatMessageList`**.**

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | Sets the Group object used in the `CometChatMessageList` for all sub-components.\nIt fetches the list of messages for this group. | 


```swift
__ syntax for set(user: User)	
messageList.set(group: group)	 __ The object which is going to be rendered in the data  item
```



---

### Background

The background is a `UIView` which is present in the backdrop for **`MessageList.`** You will be able to modify the background using the below methods:

| Method | Description | 
| ---- | ---- | 
| `set(background: [UIColor])` | This method will set the background color for **`MessageList`**, it can take an array of multiple colors for the gradient background. | 


```swift
__ syntax for set(background: [UIColor])
messageList.set(background: [UIColor.systemBackground.cgColor])
```



---

### Controller

This method will set the instance of the view controller from which the **`MessageList`** is presented.

| Method | Description | 
| ---- | ---- | 
| `set(controller: UIViewController)` | This method will set the instance of the view controller from which the **`MessageList`** is presented. | 


```swift
__ syntax for set(controller: UIViewController)
messageList.set(controller: self)
```



---

### Set Message Types

This method will set the templates of message types which user wants to display in the message list. This will take array of message type templates to show designated types. 

| Method | Description | 
| ---- | ---- | 
| `set(messageTemplates: [CometChatMessageTemplate])` | This method will set the templates of message types which user wants to display in the message list. This will take array of message type templates to show designated types. | 


```swift
__ New Template from predefined templates
let textTemplate = CometChatMessageTemplate(defaultTemplate: .text)
let imageTemplate = CometChatMessageTemplate(defaultTemplate: .image)
let fileTemplate = CometChatMessageTemplate(defaultTemplate: .file)
let locationTemplate = CometChatMessageTemplate(defaultTemplate: .location)


__ New Template

__ Creating object of new message template which you need to add support in messages
let paymentTemplate = CometChatMessageTemplate(id: "payment", name: "Make payment", icon:  UIImage(systemName: "dollarsign.square"), customView: { message
                                
     __ You need to pass the custom view here which you want to display in the message list.                  
     let paymentView = PaymentView(message: message)
     return paymentView
                                
}, options: [ CometChatMessageOption(defaultOption: .delete), CometChatMessageOption(defaultOption: .share)] ,  
                                       
onActionClick: { user , group
   __ You need to pass the action here which you want to perform when the template will get triggered from the  messages.     
   sendMessage(user: user)
})

private func sendMessage(user: User) {
  
  let paymentMessage = CustomMessage(receiverUid: user.uid, receiverType: .user, customData: ["payment-details": ["amount": "$99"]], type: "payment")
     paymentMessage?.muid = "\\(Int(Date().timeIntervalSince1970 * 1000))"
     paymentMessage?.sender = CometChatMessages.loggedInUser
     
     CometChatUIHelper.onMessageSent(message: message, status: .inProgress)
                            
  CometChat.sendCustomMessage(message: paymentMessage) { message in
                                                        
     CometChatUIHelper.onMessageSent(message: message, status: .success)
                                                        
  } onError: { error in
      CometChatUIHelper.onMessageError(message: message, error: error)
              
   }
}


__ syntax for set(messageTemplates: [CometChatMessageTemplate])
messageList.set(messageTemplates: [textTemplate, imageTemplate, fileTemplate, locationTemplate, paymentTemplate])
```



---

### Set Excluded Message Types

This method will remove the message types from the list of available message types in **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `set(excludeMessageTypes: [String])` | This method will remove the message types from the list of available message types in **`MessageList`**. | 


```swift
__ syntax for set(excludeMessageTypes: [String])
messageList.set(excludeMessageTypes: ["location", "extension_poll"])
```



---

### Set Limit

This method will specify the option to set the limit to fetch messages in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `set(limit: Int)` | This method will specify the option to set the limit to fetch messages in **`MessageList` .** | 


```swift
__ syntax for set(limit: Int)
messageList.set(limit: 30)
```



---

### Set Tags

This method will specify the option to filter the messages using tags in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `set(tags: [String])` | This method will specify the option to filter the messages using tags in **`MessageList` .** | 


```swift
__ syntax for set(tags: [String])
messageList.set(tags: ["popularity", "starred"])
```



---

### Show Unread Messages

This method will specify the option to show only unread messages while fetching the messages in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `show(onlyUnreadMessages: Bool)` | This method will specify the option to show only unread messages while fetching the messages in **`MessageList` .** | 


```swift
__ syntax for show(onlyUnreadMessages: Bool)
messageList.show(onlyUnreadMessages: true)
```



---

### Hide Messages from Blocked Users

This method will specify the option to hide messages from the blocked users while fetching the messages in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `hide(messagesFromBlockedUsers: Bool)` | This method will specify the option to hide messages from the blocked users while fetching the messages in **`MessageList` .** | 


```swift
__ syntax for hide(messagesFromBlockedUsers: Bool)
messageList.hide(messagesFromBlockedUsers: true)
```



---

### Hide Deleted Messages

This method will specify the option to hide deleted messages while fetching the messages in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `hide(deletedMessages: Bool)` | This method will specify the option to hide deleted messages while fetching the messages in **`MessageList` .** | 


```swift
__ syntax for hide(deletedMessages: Bool)
messageList.hide(deletedMessages: true)
```



---

### Hide Threaded Replies

This method will specify the option to hide threaded replies while fetching the messages in **`MessageList` .**

| Method | Description | 
| ---- | ---- | 
| `hide(threadedReplies: Bool)` | This method will specify the option to hide threaded replies while fetching the messages in **`MessageList` .** | 


```swift
__ syntax for hide(threadedReplies: Bool)
messageList.hide(threadedReplies: true)
```



---

### Error State

This method will specify the option to modify the behaviour when the message list is empty due to any interruption.

| Method | Description | 
| ---- | ---- | 
| `set(errorMessage: String)` | This method will add the message to be displayed on the UI when user faces any interruption  while fetching message | 
| `set(errorView: UIView?)` | This method will add the custom view passed by the user to on the UI when user faces any interruption  while fetching message | 
| `hide(errorMessage: Bool)` | This method will hide the error message popup when the interruption happens | 
| `set(errorStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when user faces any interruption  while fetching message | 
| `set(errorStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when user faces any interruption while fetching message | 


```swift
__ syntax for set(errorMessage: String)
messageList.set(errorMessage: "Unable to fetch Messages at this moment")

__ syntax for set(errorStateTextFont: UIFont)
messageList.set(emptyStateTextFont: UIFont.systemFont(ofSize: 18, weight: .semibold))

__ syntax for set(errorStateTextColor: UIColor)
messageList.set(emptyStateTextColor: UIColor.white)

__ syntax for hide(errorMessage: true)
messageList.hide(errorMessage: true)

__ or 

__ syntax for set(errorView: UIView?)
let errorView = UIView() __ with custom images_strings etc.
messageList.set(errorView: errorView)
```



---

### Empty State

This method will specify the option to modify the behaviour when the message list is empty due to any reason.

| Method | Description | 
| ---- | ---- | 
| `set(emptyStateMessage: String)` | This method will add the message to be displayed on the UI when the messages are empty | 
| `set(emptyStateTextFont: UIFont)` | This method will set the font for the message to be displayed on the UI when the messages are empty | 
| `set(emptyStateTextColor: UIColor)` | This method will set the color for the message to be displayed on the UI when the messages are empty | 
| `set(emptyView: UIView?)` | This method will add the custom view passed by the user to on the UI when messages are empty | 


```swift
__ syntax for set(emptyStateMessage: String)
messageList.set(emptyStateMessage: "No Messages")

__ syntax for set(emptyStateTextFont: UIFont)
messageList.set(emptyStateTextFont: UIFont.systemFont(ofSize: 26, weight: .bold))

__ syntax for set(emptyStateTextColor: UIColor)
messageList.set(emptyStateTextColor: UIColor.white)

__ or 

__ syntax for set(emptyView: UIView?)
let emptyView = UIView() __ with custom images_strings etc.
messageList.set(emptyView: emptyView)
```



---

### Add Message

This method specifies the option to add message object locally in **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `add(message: BaseMessage)` | This method specifies the option to add user object locally in **`MessageList`**. | 


```swift
__ syntax for add(message: BaseMessage)
messageList.add(message: message)
```



---

### Update Message

This method specifies the option to update message object locally in **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `update(message: BaseMessage)` | This method specifies the option to update message object locally in **`MessageList`**. | 


```swift
__ syntax for update(message: BaseMessage)
messageList.update(message: message)
```



---

### Remove Message

This method specifies the option to remove message object locally in **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `remove(message: BaseMessage)` | This method specifies the option to remove message object locally in **`MessageList`**. | 


```swift
__ syntax for remove(message: BaseMessage)
messageList.remove(message: message)
```



---

### Delete Message

This method specifies the option to delete message object in **`MessageList`**. This method will internally trigger SDK's `.deleteMessage`function to delete the message from server.

| Method | Description | 
| ---- | ---- | 
| `delete(message: BaseMessage)` | This method specifies the option to delete message object in **`MessageList`**. This method will internally trigger SDK's `.deleteMessage`function to delete the message from server. | 


```swift
__ syntax for delete(message: BaseMessage)
messageList.delete(message: message)
```



---

### Translate Message

This method will translate the `TextMessage` object present in **`MessageList`** . It will display the output on to the message bubble if it's present in the **`MessageList.`**

| Method | Description | 
| ---- | ---- | 
| `translate(message: TextMessage)` | This method will translate the `TextMessage` object present in **`MessageList`** . It will display the output on to the message bubble if it's present in the **`MessageList.`** | 


```swift
__ syntax for translate(message: BaseMessage)
messageList.translate(message: message)
```



---

### Scroll to Bottom

This method specifies the option to scroll to the bottom of the **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `scrollToBottomOnNewMessage(bool: Bool)` | This option will scroll the message list to the bottom whenever user receives new message. | 
| `scrollToBottom()` | This option can be triggered by the user if he wishes to scroll the message list to the bottom of the messages. | 


```swift
__ syntax for scrollToBottomOnNewMessage(bool: Bool)
messageList.scrollToBottomOnNewMessage(bool: true)

__ syntax for scrollToBottom()
messageList.scrollToBottom()
```



---

### Show Large Emojis

This method specifies the option to show the emojis in large sizes in Text Message bubble in **`MessageList`**.

| Method | Description | 
| ---- | ---- | 
| `showEmojiInLargerSize(bool: Bool)` | This method specifies the option to show the emojis in large sizes in Text Message bubble in **`MessageList`**. | 


```swift
__ syntax for showEmojiInLargerSize(bool: Bool)
messageList.showEmojiInLargerSize(bool: true)
```



---

### Set Message List Alignment

This method specifies the alignment of the **`MessageList`** as per user choice. It takes an enum i.e **`MessageAlignment`**. which has two cases. 

1. Standard
2. Left Aligned

| Method | Description | 
| ---- | ---- | 
| `set(messageListAlignment: MessageAlignment)` | This method specifies the alignment of the message list as per user choice. It takes an enum i.e **`MessageAlignment`**. which has two cases.\n\n**``.standard``.leftAligned``** | 


```swift
__ syntax for set(messageListAlignment: MessageAlignment)
messageList.set(messageListAlignment: .standard)
```



---

### Enable sound for Messages

This method specifies a option to enable the sounds for incoming & outgoing messages in the **`MessageList`**

| Method | Description | 
| ---- | ---- | 
| `enableSoundForMessages(bool: Bool)` | This method specifies a option to enable the sounds for incoming & outgoing messages in the **`MessageList`** | 


## 

```swift
__ syntax for set(messageListAlignment: MessageAlignment)
messageList.enableSoundForMessages(bool: true)
```



---