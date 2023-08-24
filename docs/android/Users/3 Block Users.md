## Block Users

_In other words, as a logged-in user, how do I block a user from sending me messages?_

You can block users using the `blockUsers()` method.  Once any user is blocked, all the communication to and from the respective user will be completely blocked. You can block multiple users in a single operation. The `blockUsers()` method takes a `List<String>` as a parameter which holds the list of `UIDs` to be blocked.

```java
List<String > uids = new ArrayList<>();
uids.add("UID1");
uids.add("UID2");
uids.add("UID3");
CometChat.blockUsers(uids, new CometChat.CallbackListener<HashMap<String, String>>() {
  @Override
  public void onSuccess(HashMap<String, String> resultMap) {
    __ Handle block users success.
  }

  @Override
  public void onError(CometChatException e) {
    __ Handle block users failure
  }
});
```

```kotlin
val uids = ArrayList<String>()
uids.add("UID1")
uids.add("UID2")
uids.add("UID3")

CometChat.blockUsers(uids,object:CometChat.CallbackListener<HashMap<String, String>>() {
  override fun onSuccess(resultMap: HashMap<String, String>) {
    __ Handle unblock users success.
  }

  override fun onError(e: CometChatException) {
    __ Handle unblock users failure
  }
})
```



In the `onSuccess()` callback, you receive a HashMap which contains `UIDs` as the keys and `success` or `fail` as the value based on if the block operation for the `UID` was successful or not.

## Unblock Users

_In other words, as a logged-in user, how do I unblock a user I previously blocked?_

You can unblock the already blocked users using the `unblockUsers()` method. You can unblock multiple users in a single operation. The `unblockUsers()` method takes a `List<String>` as a parameter which holds the list of `UIDs` to be unblocked.

```java
List<String > uids = new ArrayList<>();
uids.add("UID1");
uids.add("UID2");
uids.add("UID3");
CometChat.unblockUsers(uids, new CometChat.CallbackListener<HashMap<String, String>>() {
  @Override
  public void onSuccess(HashMap<String, String> resultMap) {
    __ Handle unblock users success.
  }

  @Override
  public void onError(CometChatException e) {
    __ Handle unblock users failure
  }
});
```

```kotlin
val uids = ArrayList<String>()
uids.add("UID1")
uids.add("UID2")
uids.add("UID3")

CometChat.unblockUsers(uids,object:CometChat.CallbackListener<HashMap<String, String>>() {
  override fun onSuccess(resultMap: HashMap<String, String>) {
    __ Handle unblock users success.
  }

  override fun onError(e: CometChatException) {
    __ Handle unblock users failure
  }
})
```



In the `onSuccess()` callback, you receive a HashMap which contains `UIDs` as the keys and `success` or `fail` as the value based on if the unblock operation for the `UID` was successful or not.

## Get list of blocked users

_In other words, as a logged-in user, how do I get a list of all users I've blocked?_

In order to fetch the list of blocked users, you can use the `BlockedUsersRequest` class. To use this class i.e to create an object of the `BlockedUsersRequest class`, you need to use the `BlockedUsersRequestBuilder` class. The `BlockedUsersRequestBuilder` class allows you to set the parameters based on which the blocked users are to be fetched.

The `BlockedUsersRequestBuilder` class allows you to set the below parameters:

### Set Limit

This method sets the limit i.e. the number of blocked users that should be fetched in a single iteration.

```java
BlockedUsersRequest blockedUsersRequest = new BlockedUsersRequest.BlockedUsersRequestBuilder()
  .setLimit(10)
  .build();
```

```kotlin
val blockedUsersRequest = BlockedUsersRequestBuilder()
  .setLimit(10)
  .build()
```



### Set Search Keyword

This method allows you to set the search string based on which the blocked users are to be fetched.

```java
BlockedUsersRequest blockedUsersRequest = new BlockedUsersRequest.BlockedUsersRequestBuilder()
  .setSearchKeyword("abc")
  .build();
```

```kotlin
val blockedUsersRequest = BlockedUsersRequestBuilder()
  .setSearchKeyword("abc")
  .build()
```



### Set Direction

- CometChat.BlockedUsersRequest.DIRECTION.BLOCKED_BY_ME - This will ensure that the list of blocked users only contains the users blocked by the logged in user.
- CometChat.BlockedUsersRequest.DIRECTION.HAS_BLOCKED_ME - This will ensure that the list of blocked users only contains the users that have blocked the logged in user.
- CometChat.BlockedUsersRequest.DIRECTION.BOTH - This will make sure the list of users includes both the above cases. This is the default value for the direction variable if it is not set.

```java
BlockedUsersRequest blockedUsersRequest = new BlockedUsersRequest.BlockedUsersRequestBuilder()
  .setDirection(BlockedUsersRequest.DIRECTION_BLOCKED_BY_ME)
  .build();
```

```kotlin
val blockedUsersRequest = BlockedUsersRequestBuilder()
  .setDirection(BlockedUsersRequest.DIRECTION_BLOCKED_BY_ME)
  .build()
```



Finally, once all the parameters are set in the builder class, you need to call the `build()` method to get the object of the `BlockedUsersRequest` class.

Once you have the object of the `BlockedUsersRequest` class, you need to call the `fetchNext()` method. Calling this method will return a list of `User` objects containing n number of blocked users where N is the limit set in the builder class.

```java
BlockedUsersRequest blockedUsersRequest = new BlockedUsersRequest.BlockedUsersRequestBuilder().setLimit(10).build();

blockedUsersRequest.fetchNext(new CometChat.CallbackListener<List<User>>() {
  @Override
  public void onSuccess(List<User> users) {
    for(User user : users){
      Log.e(TAG, user.getUid());
    }
  }

  @Override
  public void onError(CometChatException e) {
    Log.e(TAG, e.getMessage());
  }
});
```

```kotlin
val blockedUsersRequest = BlockedUsersRequestBuilder().setLimit(10).build()

blockedUsersRequest.fetchNext(object : CallbackListener<List<User>>() {
  override fun onSuccess(users: List<User>) {
    for (user in users) {
      Log.e(TAG, user.uid)
    }
  }

  override fun onError(e: CometChatException) {
    Log.e(TAG, e.message)
  }
})
```

