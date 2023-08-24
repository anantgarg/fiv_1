## Join a Group

In order to start participating in group conversations, you will have to join a group. You can do so using the `joinGroup()` method.

```java
private String GUID = "GUID";
private String groupType = CometChatConstants.GROUP_TYPE_PUBLIC;
private String password = "";

CometChat.joinGroup(GUID, groupType, password, new CometChat.CallbackListener<Group>() {
  @Override
  public void onSuccess(Group joinedGroup) {
    Log.d(TAG, joinedGroup.toString());
  }
  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, "Group joining failed with exception: " + e.getMessage());
  }
});
```

```kotlin
val GUID:String="GUID"
val groupType:String=CometChatConstants.GROUP_TYPE_PUBLIC
val password:String=""


CometChat.joinGroup(GUID,groupType,password,object:CometChat.CallbackListener<Group>(){
  override fun onSuccess(p0: Group?) {
    Log.d(TAG, p0.toString());
  }
  override fun onError(p0: CometChatException?) {
    Log.d(TAG, "Group joining failed with exception: " + p0?.message)
  }
})
```



The `joinGroup()` method takes the below parameters

| Parameter | Description | 
| ---- | ---- | 
| `GUID` | The GUID of the group you would like to join | 
| `groupType` | Type of the group. CometChat provides 3 types of groups viz. 1.CometChatConstants.GROUP_TYPE_PUBLIC (public)\n2.CometChatConstants.GROUP_TYPE_PASSWORD (password)\n3.CometChatConstants.GROUP_TYPE_PRIVATE (private) | 
| `password` | Password is mandatory in case of a password protected group. | 


Once you have joined a group successfully, you can send and receive messages in that group.

CometChat keeps a track of the groups joined and you do not need to join the group everytime you want to communicate in the group.

You can identify if a group is joined using the `hasJoined` parameter in the `Group` object.

## Real-time Group Member Joined Events

_In other words, as a member of a group, how do I know if someone joins the group when my app is running?_

If a user joins any group, the members of the group receive a real-time event in the `onGroupMemberJoined()` method of the `GroupListener` class.

```java
CometChat.addGroupListener(UNIQUE_LISTENER_ID, new CometChat.GroupListener() {
  @Override
  public void onGroupMemberJoined(Action action, User joinedUser, Group joinedGroup) {
    Log.d(TAG, "User joined");
  }
});
```

```kotlin
CometChat.addGroupListener(UNIQUE_LISTENER_ID, object : GroupListener() {
  override fun onGroupMemberJoined(action: Action?, joinedUser: User?, joinedGroup: Group?) {
    Log.d(TAG, "User joined")
  }
})
```



## Missed Group Member Joined Events

_In other words, as a member of a group, how do I know if someone joins the group when my app is not running?_

When you retrieve the list of previous messages if a member has joined any group that the logged-in user is a member of, the list of messages will contain an `Action` message. An `Action` message is a sub-class of `BaseMessage` class.

For the group member joined event, in the `Action` object received, the following fields can help you get the relevant information-

1. `action` - `joined`
2. `actionBy` - User object containing the details of the user who joined the group
3. `actionFor`- Group object containing the details of the group the user has joined