## Overview

`CometChatMessages` displays the chat window either for `User` or `Group` entities, and shows the list of messages where the loggedInUser has sent and received from either of the entities. `CometChatMessages` wraps up the three main components in it such as `CometChatMessageHeader`, `CometChatMessageList` & `CometChatMessageComposer`. 

![](https://uploads.developerhub.io/prod/x9W8/1a72idz85owcpig7u6gbwdy09o9sxt9byfnokolwjqpqwe5sngs05ino9dlyb4y7.png)

---

## Components

`CometChatMessages` mainly contains below components in it.

|  |  |  |  | 
| ---- | ---- | ---- | ---- | 
| 1 | **CometChatMessageHeader** | `CometChatMessageHeader` displays the `User` or `Group` information using iOS SDK's `User` or `Group object.` It also shows the typing indicator when the user starts typing in `MessageComposer`. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/message-header) | 
| 2 | **CometChatMessageList** | `CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/message-list) | 
| 3 | **CometChatMessageComposer** | `CometChatMessageComposer` is an independent and important component that allows users to send various types of messages includes text, image, video and custom messages. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/swift-chat-ui-kit/message-composer) | 


![](https://uploads.developerhub.io/prod/x9W8/oz53ildst8dal1q80amf1tqvsje6b0p6cjl6nqh0j1ht755r7z2zf5o266b1i1ib.jpg)

---

## Integration

You can launch `CometChatMessages` using below code snippet.

```swift
let cometChatMessages = CometChatMessages()
cometChatMessages.set(user: User)
self.present(cometChatMessages, animated: true)
```

```swift
let messages = CometChatMessages()
messages.set(group: Group)
self.present(messages, animated: true)
```



> If you are already using a navigation controller, you can use the `pushViewController` function instead of presenting the view controller.

---

## Methods

### Set User

This will set the `User`  object in the message list and it will fetch the list of recent messages for that particular user. 

LoggedIn user can send multiple types of messages to the user for which the chat window is opened. 

| Method | Description | 
| ---- | ---- | 
| `set(user: User)` | This will set the `User`  object in the message list and it will fetch the list of recent messages for that particular user. | 


```swift
__ syntax for set(user: User)
cometChatMessages.set(user: user)
```



---

### Set User

This will set the `Group`  object in the message list and it will fetch the list of recent messages for that particular group. 

LoggedIn user can send multiple types of messages in the group for which the chat window is opened.

| Method | Description | 
| ---- | ---- | 
| `set(group: Group)` | This will set the `User`  object in the message list and it will fetch the list of recent messages for that particular group. | 


```swift
__ syntax for set(user: User)
cometChatMessages.set(group: group)
```



---

### Set Message Types

This will set the templates of message types  to display them in messages.  LoggedIn user can send multiple types of messages in the group for which the chat window is opened.

| Method | Description | 
| ---- | ---- | 
| `set(messageTypes: [CometChatMessageTemplate])` | This will set the templates of message types  to display them in messages. | 


```swift
__ syntax for set(messageTypes: [CometChatMessageTemplate])

__ Creating object of default message templates which you need to add support in messages
 let text = CometChatMessageTemplate(type: .text)
 let image = CometChatMessageTemplate(type: .imageFromGallery)
 let file = CometChatMessageTemplate(type: .file)

cometChatMessages.set(messageTypes: [text, image, file])
```



---

### Configurations

This method will take the array of configurations and then internally it will process configurations for the required components.

```swift
__ Creating object of default message templates which you need to add support in messages
 let text = CometChatMessageTemplate(type: .text)
 let image = CometChatMessageTemplate(type: .imageFromGallery)
 let file = CometChatMessageTemplate(type: .file)
 

__ Creating object of new message template which you need to add support in messages
let payment = CometChatMessageTemplate(id: "payment", name: "Make payment", icon:  UIImage(systemName: "dollarsign.square"), customView: { message
                                
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


__creating object of MessageListConfiguration
let messageListConfiguration = MessageListConfiguration()
messageListConfiguration.set(messageTypes: [text, image, file, payment])

__creating object of MessageComposerConfiguration
let messageComposerConfiguration = MessageComposerConfiguration()
messageComposerConfiguration.set(messageTypes: [ text, image, file, payment])

                   
__Passing array of configurations to messages
cometChatMessages.set(configurations: [messageListConfiguration, messageComposerConfiguration])
```



> User can pass multiple configurations for the components underneath of **`CometChatMesages`  or the components which are launching from the events triggered from  `CometChatMesages`**

---

## Events

To handle events supported by **`CometChatMesages`** user must have to add corresponding listeners in the parent `View controller` or `Class`:

| Event | Description | 
| ---- | ---- | 
| `onMessageSent(message: BaseMessage, status: MessageStatus)` | Triggers whenever a loggedIn user sends any message, it will have two states such as: `.inProgress` & `.sent` | 
| `onMessageEdit(message: BaseMessage, status: MessageStatus)` | Triggers whenever a loggedIn user edits any message from the list of messages | 
| `onMessageDelete(message: BaseMessage, status: MessageStatus)` | Triggers whenever a loggedIn user deletes any message from the list of messages | 
| `onMessageReply(message: BaseMessage, status: MessageStatus)` | Triggers whenever a loggedIn user replies on particular message from the list of messages | 
| `onMessageRead(message: BaseMessage)` | Triggers whenever a loggedIn user reads any message. | 
| `onLiveReaction(reaction: TransientMessage)` | Triggers whenever a loggedIn clicks on live reaction | 
| `onMessageError(error: CometChatException)` | Triggers whenever a message failure happens for any reason | 
| `onVoiceCall(user: User)` | Triggers whenever a loggedIn user clicks on voice call button in user's chat window | 
| `onVoiceCall(group: Group)` | Triggers whenever a loggedIn user clicks on voice call button in groups chat window | 
| `onVideoCall(user: User)` | Triggers whenever a loggedIn user clicks on video call button in user's chat window | 
| `onVideoCall(group: Group)` | Triggers whenever a loggedIn user clicks on video call button in groups chat window | 
| `onViewInformation(user: User)` | Triggers whenever a loggedIn user clicks on info button in user's chat window | 
| `onViewInformation(group: Group)` | Triggers whenever a loggedIn user clicks on info button in groups's chat window | 
| `onMessageReact(message: BaseMessage, reaction: CometChatMessageReaction)` | Triggers whenever a loggedIn user reacts on particular message from the list of messages | 


```swift
__ View controller from your project where you want to listen events.
public class ViewController: UIViewController {
    
   public override func viewDidLoad() {
        super.viewDidLoad()
     
       __ Subscribing for the listener to listen events from message module
        CometChatMessageEvents.addListener("UNIQUE_ID", self as CometChatMessageEventListner)
    }
  
    public override func viewWillDisappear(_ animated: Bool) {
       __ Uncubscribing for the listener to listen events from message module
        CometChatMessageEvents.removeListner("UNIQUE_ID")
    }
  
  
}

 __ Listener events from message module
extension  ViewController: CometChatUserEventListener {
  
     func onMessageSent(message: BaseMessage, status: MessageStatus) {
        __ Do Stuff
    }
    
    func onMessageEdit(message: BaseMessage, status: MessageStatus) {
        __ Do Stuff
    }
    
    func onMessageDelete(message: BaseMessage, status: MessageStatus) {
        __ Do Stuff
    }
    
    func onMessageReply(message: BaseMessage, status: MessageStatus) {
        __ Do Stuff
    }
    
    func onMessageRead(message: BaseMessage) {
         __ Do Stuff
    }
    
    func onLiveReaction(reaction: TransientMessage) {
        __ Do Stuff
    }
    
    func onMessageError(error: CometChatException) {
        __ Do Stuff
    }
    
    func onVoiceCall(user: User) {
       __ Do Stuff
    }
    
    func onVoiceCall(group: Group) {
        __ Do Stuff
    }
    
    func onVideoCall(user: User) {
        __ Do Stuff
    }
    
    func onVideoCall(group: Group) {
         __ Do Stuff
    }
    
    func onViewInformation(user: User) {
        __ Do Stuff
    }
    
    func onViewInformation(group: Group) {
        __ Do Stuff
    }
    
    func onError(message: BaseMessage?, error: CometChatException) {
        __ Do Stuff
    }
    
    func onMessageReact(message: BaseMessage, reaction: CometChatMessageReaction) {
        __ Do Stuff
    }
    
}
```

