`CometChatMessageList` is one of the core UI components. It displays a list of messages and handles real-time operations. It contains the following list of possible items:

- Text messages and Rich Media if text contains URL. 
- Attachments (media or file) message.
- Location Sharing
- Collaborative Whiteboard & Document.
- Stickers
- Deleted message (only for current user)
- Sentimental Analysis (e.g. autoblocked message with inappropriate content)
- System message (e.g. some user joined a channel)
- Giphy preview
- Date separator
- Optimistic UI

You can customize the appearance of this component using custom attributes and method calls at runtime.

![](https://uploads.developerhub.io/prod/x9W8/86ibsl3zs5qhhd1yxc7nqshotw37vnp4h8o415y2x7i84ua88dq6jny0xhkr6jd4.png)

## Components

`CometChatMessageList` mainly contains below components in it.

|  | Component | Description | link | 
| ---- | ---- | ---- | ---- | 
| 1 | CometChatMessageBubble | `CometChatMessageBubble` is the reusable components which forms different types of message bubbles accordingly. | [Navigate](https://app.developerhub.io/cometchat-documentation/v3/java-chat-ui-kit/message-bubble) | 


---

## How to integrate CometChatMessageList ?

Since `CometChatMessageList` is a custom view, it can be launched by adding it into the XML layout file. `CometChatMessageList` includes various Attributes and methods to customize its UI.

```xml
<com.cometchatworkspace.components.messages.message_list.CometChatMessageList
        android:id="@+id_messageList"                                                   android:layout_width="match_parent"
        android:layout_height="match_parent"_>
```



## XML Attributes

| Parameters | Description | 
| ---- | ---- | 
| `app:alignment` | Used to set the alignmet of messages in `CometChatMessageList`. It can be either "**leftAligned**" or "**standard**" | 
| `app:actionSheetMode` | Used to set the mode of action sheet used to perform operations on messages shown in `CometChatMessageList`. It can be set either "**gridMode**" or "**listMode**" | 


```xml
<com.cometchatworkspace.components.messages.message_list.CometChatMessageList
        android:id="@+id_messageList"
        android:layout_width="match_parent"
        android:layout_height="match_parent"                    
        app:actionSheetMode="gridMode"
        app:alignment="standard"
        _>
```



### Methods

### **User**

These Method accepts SDK's users object against which old messages to be fetched 

| Methods | Description | 
| ---- | ---- | 
| setUser(User user) | Sets the User object against which old conversations are to be fetched in the message list | 


```java
__syntax for setUser
messageList.setUser(user);
```



### **Group**

These Method accepts SDK's group object  against which old messages to be fetched.

| Methods | Description | 
| ---- | ---- | 
| setGroup(Group group) | Sets the Group object against which old conversations are to be fetched in the message list | 


```java
__syntax for setGroup
messageList.setGroup(user);
```



### **Background**

You will be able to modify the background using method in the table below:

| Methods | Description | 
| ---- | ---- | 
| backgroundColor(@ColorInt int color) | This method will set the background color for message list | 


```java
__syntax for backgroundColor(@ColorInt int color)
messageList.background(Color.parseColor("#FF606D"));
```



![](https://uploads.developerhub.io/prod/x9W8/zew5j7p035dqwhw3m46wwvbuya9ao9g0fe33ng7b8ksr7agu8onegqyw4962l67v.png)

### **Filter Methods**

You will be able to filter Message List and display it as per the need by using methods in the table below:

| Methods | Description | 
| ---- | ---- | 
| hideDeleteMessage(boolean isDeleteMessageVisible) | This method will specify the option to hide/unhide deleted messages while fetching the messages in **`MessageList` .** | 
| type(String type) | Sets the message type which user want to fetch in message list. It can be either user / group | 
| guid(String id) | Sets the guid against which old conversations are to be fetched in the message list | 
| uid(String id) | Sets the uid against which old conversations are to be fetched in the message list | 


```java
__syntax for hideDeleteMessage
messageList.hideDeleteMessage(false); 

__syntax for type
messageList.type(type);

__syntax for uid
messageList.uid(id);

__syntax for guid
messageList.guid(id);
```



### **Data Operations**

These methods are used to perform data operations like add, remove and update in the Message List.

| Methods | Description | 
| ---- | ---- | 
| updateMessage(BaseMessage message) | This method will update the existing BaseMessage object from the message list | 
| add(BaseMessage message) | This method will append the BaseMessage object from the message list | 
| remove(BaseMessage message) | This method will remove the BaseMessage object from the message list | 


```java
__syntax for updateMessage
messageList.updateMessage(message);

__syntax for add
messageList.add(message);

__syntax for remove
messageList.remove(message);
```



### **Scroll to Bottom**

This Method will scroll to the last message of the message list

| Method | Description | 
| ---- | ---- | 
| scrollToBottom() | This option can be triggered by the user if he wishes to scroll the message list to the bottom. | 


```java
__syntax for scrollToBottom
messageList.scrollToBottom();
```



### **Message Receipt**

This Method will set the message Receipt in UI based on  MessageReceipt object.

| Method | Description | 
| ---- | ---- | 
| setMessageReceipt(MessageReceipt receipt) | This method will accept the MessageReceipt object and update the Receipt UI for that perticular message. | 


```java
__syntax for setMessageReceipt
messageList.setMessageReceipt(receipt);
```



### **Action Sheet Mode**

 Used to set the mode of action sheet.

| Method | Description | 
| ---- | ---- | 
| actionSheetMode(@ActionSheet.LayoutMode String actionSheetMode) | Used to set the mode of action sheet used to perform operations on messages shown in `CometChatMessageList`. It can be set either "**gridMode**" or "**listMode**" | 


```java
__syntax for setMessageReceipt
messageList.actionSheetMode(ActionSheet.LayoutMode.gridMode);
```



### **Message Alignment**

The Message List alignment can be set by using method in the table below:

| Method | Description | 
| ---- | ---- | 
| messageListAlignment(@MessageListAlignment String alignment) | Used to set message bubbles in a list left or standard align | 


```java
__to LEFT_ALIGN Messages
messageList.messageListAlignment(CometChatMessageList.LEFT_ALIGNED);

__to STANDARD_ALIGN Messages
messageList.messageListAlignment(CometChatMessageList.STANDARD);
```



![](https://uploads.developerhub.io/prod/x9W8/8hkjpaq0imr87cv0gu95iedpf2gbgdq4mocmtil4o121ph71y4w77jiiyeb7leyu.png)

### **Configuration**

This method is used to configure there child component, Here child components is CometChatMessageBubble 

| Method | Description | 
| ---- | ---- | 
| setConfiguration(CometChatConfigurations configuration) | this method will require the object of `MessageBubbleConfiguration` as a parameter to configure CometChatMessageBubble. | 


```java
__syntax to create MessageInputData object
MessageInputData messageInputData=new MessageInputData(true,true,true,true,true);

__syntax to create MessageBubbleConfiguration object
MessageBubbleConfiguration messageBubbleConfiguration=new MessageBubbleConfiguration()
.setSentMessageInputData(messageInputData);

__syntex to set configuration in messageList 
messageList.setConfiguration(messageBubbleConfiguration);
```

