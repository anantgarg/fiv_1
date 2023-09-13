CometChatUserEvents emits events when the logged-in user executes some action on another user

It contains the following properties and methods

## usersListener

This is a HashMap that contains components listening to user events in key value pairs

### Type

`Map<String, CometChatUserEvents>`

---

## addUsersListener

this method stores the passed listenerClass against the passed listenerId in the usersListener.

### Signature

```java
addUserListener(String listenerId, CometChatUserEvents listenerClass)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key to store the component against | 
| listenerClass | CometChatUserEventListener | the component listening to user events | 


---

removeUsersListener

this method removes the entry with the passed passed listenerId from the usersListener.

### Signature

```java
removeListener(String listenerId)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key of the entry to remove | 


---

## ccUserBlocked

This method is used to perform some task when the logged-in user has blocked a user

### Signature

```java
ccUserBlocked(User user)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| user | User | the user that has been blocked | 


---

## ccUserUnblocked

This method is used to perform some task when the logged-in user has unblocked a blocked user.

### Signature

```java
ccUserUnblocked(User user)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| user | User | the user that has been unblocked | 


### Return Type

`void`

---

## Emitting User Events

There are two types of user event listeners, one is for the SDK, which listens for events emitted from the backend for actions taken by users other than the logged in user and second, the events specific to the UI Kit which listens for events emitted from the client side for actions made by the logged-in user. The code snippets shared below contains how to emit such client-side user events to inform other UI components in your project that a user has been blocked or unblocked, the methods being used are static and hence they can be called without having to create an instance of CometChatUserEvents class.

```java
___pass the [User] object of the user which has been blocked by the logged in user
for (CometChatUserEvents events : CometChatUserEvents.userEvents.values()) {
            events.ccUserBlocked(user);
        }

___pass the [User] object of the user which has been unblocked by the logged in user
for (CometChatUserEvents events : CometChatUserEvents.userEvents.values()) {
            events.ccUserUnblocked(user);
        }
```



---

## Listening to User Events

Here we will go through how anyone can listen to these client-side User Events to update the state of the UI accordingly.

| Events | Description | 
| ---- | ---- | 
| `ccUserBlocked` | This will get triggered when the logged in user blocks another user | 
| `ccUserUnblocked` | This will get triggered when the logged in user unblocks another user | 


```java
CometChatUserEvents.addUserListener(LISTENERS_TAG, new CometChatUserEvents() {
            @Override
            public void ccUserBlocked(User user) {
                
            }

            @Override
            public void ccUserUnblocked(User user) {
                
            }
        });
```

