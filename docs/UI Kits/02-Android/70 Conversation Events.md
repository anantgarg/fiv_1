CometChatConversationEvents emits events when the logged-in user executes some action on a conversation object

It contains the following properties and methods

## conversationListListener

This is a HashMap that contains components listening to user events in key value pairs

### Type

`Map<String, CometChatConversationEvents>`

---

## addConversationsListListener

this method stores the passed listenerClass against the passed listenerId in the conversationListListener.

### Signature

```java
addListener(String listenerId, CometChatConversationEvents listenerClass)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key to store the component against | 
| listenerClass | CometChatConversationEvents | the component listening to conversation events | 


---

## removeConversationListListener

this method removes the entry with the passed passed listenerId from the conversationListListener.

### Signature

```java
removeListener(String listenerId)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key of the entry to remove | 


### Return Type

`void`

---

## ccConversationDeleted

This method is used to perform some task when the logged-in user has deleted a conversation

### Signature

```java
ccConversationDeleted(Conversation conversation)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| conversation | Conversation | the user that has been deleted | 


---

## Emitting Conversation Events

Here we will go through how to emit events specific to the UI Kit which listens for events emitted from the client side for actions made by the logged-in user. The code snippets shared below contains how to emit such client-side conversation events to inform other UI components in a project that a conversation has been deleted, the methods being used are static and hence they can be called without having to create an instance of CometChatConversationEvents class.

```java
for (CometChatConversationEvents e : CometChatConversationEvents.conversationEvents.values()) {
                        e.ccConversationDeleted(conversation);
}
```



---

## Listening to Conversation Events

Here we will go through how anyone can listen to these client-side Conversation Events to update the state of the UI accordingly.

| Event | Description | 
| ---- | ---- | 
| `ccConversationDeleted` | This event will be triggered when the logged in user deletes a conversation | 


```java
CometChatConversationEvents.addListener("LISTENERS_TAG", new CometChatConversationEvents() {
            @Override
            public void ccConversationDeleted(Conversation conversation) {
               
            }
        });
```

