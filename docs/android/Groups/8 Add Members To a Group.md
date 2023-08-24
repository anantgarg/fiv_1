## Add Members to Group

You can add members to the group using the `addMembersToGroup()` method. This method takes the below parameters:

1. `GUID`  - GUID of the group users are to be added to.
2. `List<GroupMember> members` - This is a list of `GroupMember` objects. In order to add members, you need to create an object of the `GroupMember` class. The `UID` and the scope of the `GroupMember` are mandatory.
3. `List<String> bannedMembers` - This is the list of `UIDs` that need to be banned from the group. This can be set to `null` if there are no members to be banned.
4. Callback

```java
List<GroupMember> members = new ArrayList<>();
members.add(new GroupMember("uid1",CometChatConstants.SCOPE_MODERATOR));
members.add(new GroupMember("uid2", CometChatConstants.SCOPE_ADMIN));

CometChat.addMembersToGroup("GUID", members, null, new CometChat.CallbackListener<HashMap<String, String>>(){
  @Override
  public void onSuccess(HashMap<String, String> successMap) {
    Log.d("CometChatActivity", success);
  }

  @Override
  public void onError(CometChatException e) {
    Toast.makeText(CometChatActivity.this,
                   e.getMessage(),Toast.LENGTH_LONG).show();
  }
});
```

```kotlin
val member:MutableList<GroupMember> = arrayListOf()     
member.add(GroupMember(UID,CometChatConstants.SCOPE_PARTICIPANT))

CometChat.addMembersToGroup(GUID,member,null,object :CometChat.CallbackListener<HashMap<String,String>>(){

  override fun onSuccess(p0: HashMap<String, String>?) {
  
  }

  override fun onError(p0: CometChatException?) {

  }
})
```



In the `onSuccess()` method of the `CallbackListener`, you will receive a HashMap which will contain the `UID` of the users and the value will either be `success` or an error message describing why the operation to add the user to the group or ban the user failed.

## Real-Time Group Member Added Events

_In other words, as a member of a group, how do I know when someone is added to the group when my app is running?_

> When a group member is added by another member, this event is triggered. When a user joins a group on their own, the joined event is triggered.

To receive real-time events whenever a new member is added to a group, you need to implement the  `onMemberAddedToGroup()` methods of the `GroupListener` class.

- `onMemberAddedToGroup()` - This method is triggered when any user is added to the group so that the logged-in user is informed of the other members added to the group.

```java
CometChat.addGroupListener("LISTENER_ID", new CometChat.GroupListener() {
  @Override
  public void onMemberAddedToGroup(Action action, User addedby, User userAdded, Group addedTo) {
    Log.d("onMemberAddedToGroup", action.getMessage());
  }
});
```

```kotlin
CometChat.addGroupListener("LISTENER_ID", object : CometChat.GroupListener() {
  override fun onMemberAddedToGroup(action: Action, addedby: User, userAdded: User, addedTo: Group) {
    Log.d("onMemberAddedToGroup", action.message)
  }
})
```



## Member Added to Group event in Message History

_In other words, as a member of a group, how do I know when someone is added to the group when my app is not running?_

When you retrieve the list of previous messages if a member has been added to any group that the logged-in user is a member of, the list of messages will contain an `Action` message. An `Action` message is a sub-class of `BaseMessage` class.

For the group member added event, in the `Action` object received, the following fields can help you get the relevant information-

1. `action` - `added`
2. `actionOn` - User object containing the details of the user who was added to the group
3. `actionBy` - User object containing the details of the user who added the member to the group
4. `actionFor` - Group object containing the details of the group to which the member was added