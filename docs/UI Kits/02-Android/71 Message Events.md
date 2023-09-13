CometChatMessageEvents emits events when the logged-in user executes some action involving any message object.

It contains the following properties and methods:

## messagesListener

This is a HashMap that contains components listening to message events in key value pairs

### Type

`Map<String, CometChatMessageEvents>`

---

## addMessagesListener

this method stores the passed listenerClass against the passed listenerId in the messagesListener.

### Signature

```java
addListener(String listenerId, CometChatMessageEvents listenerClass)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key to store the component against | 
| listenerClass | CometChatMessageEvents | the component listening to message events | 


---

## removeMessagesListener

this method removes the entry with the passed listenerId from the messagesListener.

### Signature

```java
removeListener(String listenerId)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key of the entry to remove | 


---

## ccMessageSent

This method is used to perform some task when the logged-in user has sent a message

### Signature

```java
ccMessageSent(BaseMessage baseMessage, @MessageStatus int status)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | BaseMessage | the message that has been sent | 
| messageStatus | MessageStatus | the status of the message, it can be `inProgress`, `sent` or `error` | 


---

## ccMessageEdited

This method is used to perform some task when the logged-in user has edited a message

### Signature

```java
ccMessageEdited(BaseMessage baseMessage, @MessageStatus int status)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | BaseMessage | the message that has been sent | 
| messageStatus | MessageEditStatus | the status of the message, it can be `inProgress` or `success` | 


---

## ccMessageDeleted

This method is used to perform some task when the logged-in user has deleted a message

### Signature

```java
ccMessageDeleted(BaseMessage baseMessage)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | BaseMessage | the message that has been sent | 
| messageStatus | EventStatus | the status of the message, it can be `inProgress` or `success` | 


---

## ccMessageRead

This method is used to perform some task when the logged-in user has read a message

### Signature

```java
ccMessageRead(BaseMessage baseMessage)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | BaseMessage | the message that has been read | 


---

## ccLiveReaction

This method is used to perform some task when the logged-in user has a sent a transient message

### Signature

```java
ccLiveReaction(@DrawableRes int icon)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| icon | @DrawableRes int | the image to send as transient message | 


---

## Emitting Message Events

There are two types of message event listeners, one is for the SDK, which listens for events emitted from the backend for actions taken by users other than the logged in user; and second, the events specific to the UI Kit which listens for events emitted from the client side for actions made by the logged-in user. The code snippets shared below contains how to emit such client-side message events to inform other UI components in a project.

```java
_*emit this when the logged in user has sent a message. Pass the object of the [TextMessage], [MediaMessage] or [CustomMessage] being sent and the [MessageStatus] if [inProgress], [sent] successfully or failed with [error]*_
   for (CometChatMessageEvents event : CometChatMessageEvents.messageEvents.values()) {
            event.ccMessageSent(message, status);
        }

  _*emit this for when a message is edited by logged-in user. Pass the object of the [TextMessage], [MediaMessage] or [CustomMessage] being edited and the [MessageEditStatus] if [inProgress] or [success]*_
   for (CometChatMessageEvents event : CometChatMessageEvents.messageEvents.values()) {
            event.ccMessageEdited(message, status);
        }

  _*emit this when a message is being deleted by logged-in user. Pass the object of the [TextMessage], [MediaMessage] or [CustomMessage] being deleted and also pass the [EventStatus] if [inProgress] or [success]*_
  for (CometChatMessageEvents event : CometChatMessageEvents.messageEvents.values()) {
            event.ccMessageDeleted(message);
        }

  _*emit this when a message is read by logged-in user. Pass the object of the [TextMessage], [MediaMessage] or [CustomMessage] being read*_
 for (CometChatMessageEvents event : CometChatMessageEvents.messageEvents.values()) {
            event.ccMessageRead(message);
        }

  _*emit this when a transient message is sent by logged-in user. Pass a [String] asset image of the Live Reaction to show in the animation*_
  for (CometChatMessageEvents event : CometChatMessageEvents.messageEvents.values()) {
            event.ccLiveReaction(icon);
        }
```



---

## Listening to Message Events

Here we will go through how anyone can listen to these client-side Message Events to update the state of the UI accordingly.

| Events | Description | 
| ---- | ---- | 
| [`ccMessageSent`](`ccMessageSent`) | Triggers whenever a loggedIn user sends any message, it will have two states such as: inProgress & sent | 
| [`ccMessageEdited`](`ccMessageEdited`) | Triggers whenever a loggedIn user edits any message from the list of messages .it will have two states such as: inProgress & sent | 
| [`ccMessageDeleted`](`ccMessageDeleted`) | Triggers whenever a loggedIn user deletes any message from the list of messages | 
| [`ccMessageRead`](`ccMessageRead`) | Triggers whenever a loggedIn user reads any message. | 
| [`ccLiveReaction`](`ccLiveReaction`) | Triggers whenever a loggedIn clicks on live reaction | 


```java
CometChatMessageEvents.addListener("LISTENER_ID", new CometChatMessageEvents() {
            @Override
            public void ccMessageSent(BaseMessage baseMessage, int status) {
                super.ccMessageSent(baseMessage, status);
            }

            @Override
            public void ccMessageEdited(BaseMessage baseMessage, int status) {
                super.ccMessageEdited(baseMessage, status);
            }

            @Override
            public void ccMessageDeleted(BaseMessage baseMessage) {
                super.ccMessageDeleted(baseMessage);
            }

            @Override
            public void ccMessageRead(BaseMessage baseMessage) {
                super.ccMessageRead(baseMessage);
            }

            @Override
            public void ccLiveReaction(int icon) {
                super.ccLiveReaction(icon);
            }
        });
```

