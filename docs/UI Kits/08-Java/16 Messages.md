The `CometChatMessages` component is a fragment component in the UI Kit Library that is used to handle messages for users and groups.`CometChatMessages` wraps up the three main components in it such as `CometChatMessageHeader`, `CometChatMessageList` & `CometChatMessageComposer`.

![](https://res.cloudinary.com/developerhub/image/upload/v1645621784/v2_5163/ehrsn5qw7xxmtwno3die.png)

---

## Components

CometChatMessages mainly contains below components in it.

|  | Components | Description | link | 
| ---- | ---- | ---- | ---- | 
| 1 | CometChatMessageHeader | `CometChatMessageHeader` displays the `User` or `Group` information using iOS SDK's `User` or `Group object.` It also shows the typing indicator when the user starts typing in `MessageComposer`. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/message-header) | 
| 2 | CometChatMessageList | `CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/cometchatmessagelist) | 
| 3 | CometChatMessageComposer | `CometChatMessageComposer` is an independent and critical component that allows users to compose and send various types of messages includes text, image, video and custom messages. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/messagecomposer) | 


---

## How to use CometChatMessages?

The benefit of a fragment component is easy integration. You can create a reference  `CometChatMessages` object and use its method to pass required parameters like `id`, `type`, etc., and later pass the reference of fragment inside your `fragmentManager`.

```java
CometChatMessages messagesFragment = new CometChatMessages();
__Check for user or group
if (user!=null)
  messagesFragment.setUser(user);
else if (group!=null)
  messagesFragment.setGroup(group);
getSupportFragmentManager().beginTransaction().replace(R.id.chat_fragment, messagesFragment).commit();
```



#### CometChatMessagesActivity

`CometChatMessagesActivity` is an Activity class that helps you launch the messages screen easily. With one line of code, you can launch Messages Screen for 1-1 chats & group chats

```java
__To launch user chat
CometChatMessagesActivity.launch(this,user);

__To launch group chat
CometChatMessagesActivity.launch(this,group);
```



## Methods

### **User**

This will set the `User` object in the message list and it will fetch the list of recent messages for that particular user.

LoggedIn user can send multiple types of messages to the user for which the chat window is opened.

| Method | Description | 
| ---- | ---- | 
| setUser(User user) | Used to pass the user object in `CometChatMessages` . | 
| setUser(String uid) | Used to pass the user id in `CometChatMessages`. | 


```java
__syntax for setUser using User object
messagesFragment.setUser(user);

__syntax for setUser using uid 
messagesFragment.setUser(uid);
```



### **Group**

This will set the `Group` object in the message list and it will fetch the list of recent messages for that particular group.

LoggedIn user can send multiple types of messages in the group for which the chat window is opened.

| Methods | Description | 
| ---- | ---- | 
| setGroup(Group group) | Used to pass the group object in `CometChatMessages` . | 
| setGroup(String guid) | Used to pass the group id in `CometChatMessages`. | 


```java
__syntax for setGroup using User object
messagesFragment.setGroup(group);

__syntax for setGroup using uid 
messagesFragment.setGroup(guid);
```



### **UpdateList**

This Method is used to to append sdk's BaseMessage object to the MessageList.

| Method | Description | 
| ---- | ---- | 
| updateList(BaseMessage message) | Used to append message object to the MessageList. | 


```java
__syntax for updateList
messagesFragment.updateList(message);
```



### **Background**

You will be able to modify the background using the below methods:

| Methods | Description | 
| ---- | ---- | 
| background(Drawable drawable) | Used to set Drawable in background. | 
| background(@ColorInt int color) | Used to set background color in background. | 


```java
__ syntax for setBackground(Drawable drawable)
messagesFragment.setBackground(getResources().getDrawable(R.drawable.background));

__ syntax for setBackground(@ColorInt int color)
messagesFragment.setBackgroundColor(getResources().getColor(R.color.background));
```



### **Configuration**

These methods are used to configure there child component, Here child component are `CometChatComposer`, `CometChatMessageList` and  `CometChatMessageHeader` .

| Methods | Description | 
| ---- | ---- | 
| setConfiguration(CometChatConfigurations configuration) | This method is used to configure the properties of the child Component | 
| setConfiguration(List&lt;CometChatConfigurations&gt; configurations) | This method is used to configure the properties of multiple child Components of the CometChatUsers | 


```java
MessageListConfiguration configuration=new MessageListConfiguration()
        .setDeleteMessageHidden(false)
        .setMessageAlignment(CometChatMessageList.STANDARD);
messagesFragment.setConfiguration(configuration);
```



below code snippet is showing how to pass configuration to the CometChatMessages module if the user is using CometChatMessagesActivity 

```java
MessageListConfiguration configuration=new MessageListConfiguration()
        .setDeleteMessageHidden(false)
        .setMessageAlignment(CometChatMessageList.STANDARD); 

__To launch user chat with CometChatMessageConfigurations
CometChatMessagesActivity.launch(ComponentLoadActivity.this,user,userConfiguration);

__To launch group chat
CometChatMessagesActivity.launch(ComponentLoadActivity.this,group,groupConfiguration);
```



> Similarly user can create the object for  ComposerConfiguration and HeaderConfiguration and pass it to configuration , if he/she wants to configure those component as well.

## Events

To handle events supported by CometChatMessages you have to add corresponding listeners in the parent `Fragment` or `Activity` using CometChatMessageEvents

| Event | Description | 
| ---- | ---- | 
| `onMessageSent(BaseMessage baseMessage, @MessageStatus int status)` | Triggers whenever a loggedIn user sends any message, it will have two states such as: \n\nIN_PROGRESS & _SUCCESS_ | 
| `onMessageEdit(BaseMessage baseMessage, @MessageStatus int status)` | Triggers whenever a loggedIn user edits any message from the list of messages | 
| `onMessageDelete(BaseMessage baseMessage, CometChatMessageList cometChatMessageList)` | Triggers whenever a loggedIn user deletes any message from the list of messages | 
| `onMessageReply(BaseMessage baseMessage, @MessageStatus int status)` | Triggers whenever a loggedIn user replies on particular message from the list of messages | 
| `onMessageRead(BaseMessage baseMessage)` | Triggers whenever a loggedIn user reads any message. | 
| `onLiveReaction(String type, Reaction emoji)` | Triggers whenever a loggedIn clicks on live reaction | 
| `onMessageError(CometChatException e)` | Triggers whenever a message failure happens for any reason | 
| `onVoiceCall(AppEntity user_or_group)` | Triggers whenever a loggedIn user clicks on voice call button in user's or group's chat window | 
| `onVideoCall(AppEntity user_or_group)` | Triggers whenever a loggedIn user clicks on video call button in user's or group's chat window | 
| `onViewInformation(AppEntity user_or_group)` | Triggers whenever a loggedIn user clicks on info button in user's or group's chat window | 
| `onMessageReact(BaseMessage baseMessage, Reaction emoji)` | Triggers whenever a loggedIn user reacts on particular message from the list of messages | 


```java
CometChatMessageEvents.addListener("UNIQUE_ID", new CometChatMessageEvents() {
            @Override
            public void onMessageSent(BaseMessage baseMessage, int status) {
                super.onMessageSent(baseMessage, status);
            }
            @Override
            public void onMessageEdit(BaseMessage baseMessage, int status) {
                super.onMessageEdit(baseMessage, status);
            }
            @Override
            public void onMessageDelete(BaseMessage baseMessage, CometChatMessageList cometChatMessageList) {
                super.onMessageDelete(baseMessage, cometChatMessageList);
            }
            @Override
            public void onMessageReply(BaseMessage baseMessage, int status) {
                super.onMessageReply(baseMessage, status);
            }

            @Override
            public void onMessageRead(BaseMessage baseMessage) {
                super.onMessageRead(baseMessage);
            }
            @Override
            public void onLiveReaction(String type, Reaction emoji) {
                super.onLiveReaction(type, emoji);
            }
            @Override
            public void onMessageError(CometChatException e) {
                super.onMessageError(e);
            }

            @Override
            public void onVoiceCall(AppEntity user_or_group) {
                super.onVoiceCall(user_or_group);
            }

            @Override
            public void onVideoCall(AppEntity user_or_group) {
                super.onVideoCall(user_or_group);
            }

            @Override
            public void onViewInformation(AppEntity user_or_group) {
                super.onViewInformation(user_or_group);
            }
            @Override
            public void onMessageReact(BaseMessage baseMessage, Reaction emoji) {
                super.onMessageReact(baseMessage, emoji);
            }
            
        });
```

