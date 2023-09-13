CometChatGroupEvents emits events when the logged-in user executes some action on a group or group member

It contains the following properties and methods:

## groupsListener

This is a HashMap that contains components listening to group events in key value pairs

### Type

`Map<String, CometChatGroupEvents>`

---

## addGroupsListener

this method stores the passed listenerClass against the passed listenerId in the groupsListener.

### Signature

```java
addGroupListener(String listenerId, CometChatGroupEvents listenerClass)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key to store the component against | 
| listenerClass | CometChatGroupEventListener | the component listening to group events | 


---

## removeGroupsListener

this method removes the entry with the passed passed listenerId from the groupsListener.

### Signature

```java
removeListener(String listenerId)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| listenerId | String | the key of the entry to remove | 


---

## ccGroupCreated

This method is used to perform some task when the logged-in user has created a group

### Signature

```java
ccGroupCreated(Group group)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| group | Group | the new group that has been created | 


---

## ccGroupDeleted

This method is used to perform some task when the logged-in user has deleted a group.

### Signature

```java
ccGroupDeleted(Group group)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| group | Group | the group that has been deleted | 


---

## ccGroupLeft

This method is used to perform some task when the logged-in user has left a group.

### Signature

```java
ccGroupLeft(Action message, User leftUser, Group leftGroup)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | Action | the action message to display in the message list | 
| leftUser | User | the user that has left the group | 
| leftGroup | Group | the group from which the logged-user has left | 


---

ccGroupMemberScopeChanged

This method is used to perform some task when the logged-in user has changed the scope of a member of a group.

### Signature

```java
ccGroupMemberScopeChanged(Action message,User updatedUser, String scopeChangedTo, String scopeChangedFrom, Group group)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | Action | the action message to display in the message list | 
| updatedUser | User | the user whose scope has been changed | 
| scopeChangedTo | String | the new scope | 
| scopeChangedFrom | String | the old scope | 
| group | Group | the group from where the scope change has occurred | 


---

## ccGroupMemberBanned

This method is used to perform some task when the logged-in user has banned a user from the group.

### Signature

```java
ccGroupMemberBanned(Action message, User bannedUser, User bannedBy, Group bannedFrom)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | Action | the action message to display in the message list | 
| bannedUser | User | the user that has been banned | 
| bannedBy | User | the user who has banned | 
| bannedFrom | Group | the group from which the user has been banned | 


---

## ccGroupMemberKicked

This method is used to perform some task when the logged-in user has kicked a user from the group.

### Signature

```java
ccGroupMemberKicked(Action message, User kickedUser, User kickedBy, Group kickedFrom)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | Action | the action message to display in the message list | 
| kickedUser | User | the banned user that has been kicked | 
| kickedBy | User | the user who has kicked | 
| kickedFrom | Group | the group from which the user has been kicked | 


---

## ccGroupMemberUnbanned

This method is used to perform some task when the logged-in user has unbanned a banned user from a group.

### Signature

```java
ccGroupMemberUnbanned(Action message, User unbannedUser, User unbannedBy, Group unbannedFrom)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| message | Action | the action message to display in the message list | 
| unbannedUser | User | the banned user that has been unbanned | 
| unbannedBy | User | the user who has unbanned | 
| unbannedFrom | Group | the group from which the banned user has been unbanned | 


---

## ccGroupMemberJoined

This method is used to perform some task when the logged-in user has joined a group.

### Signature

```java
ccGroupMemberJoined(User joinedUser, Group joinedGroup)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| joinedUser | User | the user that has been unblocked | 
| joinedGroup | Group | the group the users have been added to | 


---

## ccGroupMemberAdded

This method is used to perform some task when the logged-in user has added new members to the group

### Signature

```java
ccGroupMemberAdded(List<Action> messages,List<User> usersAdded, Group groupAddedIn,User addedBy)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| messages | List&lt;Action&gt; messages | a list of action messages to display in the message list | 
| usersAdded | List&lt;User&gt; | the list of users added | 
| groupAddedIn | Group | the group the users have been added to | 
| addedBy | User | the user who has added those new members | 


---

ccOwnershipChanged

This method is used to perform some task when the logged-in user has transferred their ownership of a group.

### Signature

```java
ccOwnershipChanged(Group group, GroupMember newOwner)
```



### Parameters

| Parameters | Type | Description | 
| ---- | ---- | ---- | 
| group | Group | the group where the ownership has been changed | 
| newOwner | GroupMember | the group member who has been made owner of the group | 


---

## Emitting Group Events

There are two types of group event listeners, one is for the SDK, which listens for events emitted from the backend for actions taken by users other than the logged in user and second, the events specific to the UI Kit which listens for events emitted from the client side for actions made by the logged-in user. The code snippets shared below contains how to emit such client-side group events to inform other UI components in a project that a group has been created or deleted or new members have been added to the group, the logged in user themselves have joined a group, members being banned by the logged in user or the change of ownership or scope of a group member, the methods being used are static and hence they can be called without having to create an instance of CometChatGroupEvents class.

```java
___you need to pass the [Group] object of the group which is created
  for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
                    events.ccGroupCreated(group);
}
___you need to pass the [Group] object of the group which is deleted
  for (CometChatGroupEvents e : CometChatGroupEvents.groupEvents.values()) {
                        e.ccGroupDeleted(group);
 }
___emit this when logged in user leaves the group. Pass an [Action] message to display on the [CometChatMessageList], [User] object of the logged-in user, and the [Group] object of the group the logged-in user is leaving
  for (CometChatGroupEvents e : CometChatGroupEvents.groupEvents.values()) {
                        e.ccGroupLeft(action, loggedInUser, group);
}
___emit this when group member's scope is changed by logged in user. Pass an [Action] message to display on the [CometChatMessageList], [User] object of the group member whose scope has been changed, a [String] containing the new scope, a [String] containing the previous scope and the [Group] object of the group where the logged-in user has changed the scope of another [GroupMember]
for (CometChatGroupEvents e : CometChatGroupEvents.groupEvents.values()) {
                    e.ccGroupMemberScopeChanged(action, updateMember, scopeChangedTo, updateMember.getScope(), group);
 }

  ___emit this when group member is banned from the group by logged in user. Pass an [Action] message to display on the [CometChatMessageList], [User] object of the group member who was banned by the logged in user, [User] object of the logged-in user since they are the one banning, and the [Group] object of the group where the logged-in user has banned another [GroupMember]
 for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
                    events.ccGroupMemberBanned(action, groupMember, loggedInUser, group);
  }
  ___emit this when group member is kicked from the group by logged in user. Pass an [Action] message to display on the [CometChatMessageList], [User] object of the group member who was kicked by the logged in user, [User] object of the logged-in user since they are the one kicking, and the [Group] object of the group where the logged-in user has kicked another [GroupMember]
for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
                    events.ccGroupMemberKicked(action, groupMember, loggedInUser, group);
 }

  ___emit this when a banned group member is unbanned from group by logged in user. Pass an [Action] message to display on the [CometChatMessageList], [User] object of the banned member who was unbanned by the logged in user, [User] object of the logged-in user since they are the one unbanning, and the [Group] object of the group where the logged-in user has unbanned the banned member
for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
     events.ccGroupMemberUnBanned(action, groupMember, CometChat.getLoggedInUser(), group);
  }
  ___emit this when logged in user has joined a group successfully. Pass the [User] object of the logged-in user since they are the one joining the group and the [Group] object of the group the logged in user has joined
for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
                    events.ccGroupMemberJoined(CometChat.getLoggedInUser(), joinedGroup);
  }
  ___emit this when members are added to a group by the logged in user. Pass a list of [Action] messages to display on the [CometChatMessageList], a list of [User]s added to the group and the [Group] object of the group the logged in user has added those users in and the [User] object of the logged-in user since they are the one adding the members
for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
                        events.ccGroupMemberAdded(actions, members, group, CometChat.getLoggedInUser());
                    }
  ___emit this when ownership is changed by logged in user. Pass the [Group] object of the group the logged in user used to own before transferring the ownership and the [GroupMember] object of the new owner of the group to whom the logged in user has transferred the ownership
 for (CometChatGroupEvents events : CometChatGroupEvents.groupEvents.values()) {
            events.ccOwnershipChanged(group, newOwner);
        }
```



---

## Listening to Group Events

Here we will go through how anyone can listen to these client-side Group Events to update the state of the UI accordingly.

| Events | Description | 
| ---- | ---- | 
| `ccGroupCreated` | This will get triggered when the logged in user creates a group | 
| `ccGroupDeleted` | This will get triggered when the logged in user deletes a group | 
| `ccGroupLeft` | This will get triggered when the logged in user leaves a group | 
| `ccGroupMemberScopeChanged` | This will get triggered when the logged in user changes the scope of another group member | 
| `ccGroupMemberBanned` | This will get triggered when the logged in user bans a group member from the group | 
| `ccGroupMemberKicked` | This will get triggered when the logged in user kicks another group member from the group | 
| `ccGroupMemberUnbanned` | This will get triggered when the logged in user unbans a user banned from the group | 
| `ccGroupMemberJoined` | This will get triggered when the logged in user joins a group | 
| `ccGroupMemberAdded` | This will get triggered when the logged in user add new members to the group | 
| `ccOwnershipChanged` | This will get triggered when the logged in user transfer the ownership of their group to some other member | 


```java
CometChatGroupEvents.addGroupListener("LISTENER_TAG", new CometChatGroupEvents() {
            @Override
            public void ccGroupCreated(Group group) {
                super.ccGroupCreated(group);
            }

            @Override
            public void ccGroupDeleted(Group group) {
                super.ccGroupDeleted(group);
            }

            @Override
            public void ccGroupLeft(Action actionMessage, User leftUser, Group leftGroup) {
                super.ccGroupLeft(actionMessage, leftUser, leftGroup);
            }

            @Override
            public void ccGroupMemberJoined(User joinedUser, Group joinedGroup) {
                super.ccGroupMemberJoined(joinedUser, joinedGroup);
            }

            @Override
            public void ccGroupMemberAdded(List<Action> actionMessages, List<User> usersAdded, Group userAddedIn, User addedBy) {
                super.ccGroupMemberAdded(actionMessages, usersAdded, userAddedIn, addedBy);
            }

            @Override
            public void ccGroupMemberKicked(Action actionMessage, User kickedUser, User kickedBy, Group kickedFrom) {
                super.ccGroupMemberKicked(actionMessage, kickedUser, kickedBy, kickedFrom);
            }

            @Override
            public void ccGroupMemberBanned(Action actionMessage, User bannedUser, User bannedBy, Group bannedFrom) {
                super.ccGroupMemberBanned(actionMessage, bannedUser, bannedBy, bannedFrom);
            }

            @Override
            public void ccGroupMemberUnBanned(Action actionMessage, User unbannedUser, User unBannedBy, Group unBannedFrom) {
                super.ccGroupMemberUnBanned(actionMessage, unbannedUser, unBannedBy, unBannedFrom);
            }

            @Override
            public void ccGroupMemberScopeChanged(Action actionMessage, User updatedUser, String scopeChangedTo, String scopeChangedFrom, Group group) {
                super.ccGroupMemberScopeChanged(actionMessage, updatedUser, scopeChangedTo, scopeChangedFrom, group);
            }

            @Override
            public void ccOwnershipChanged(Group group, GroupMember newOwner) {
                super.ccOwnershipChanged(group, newOwner);
            }

        });
```

