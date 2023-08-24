_In other words, as a logged-in user, how do I transfer the ownership of any group if I am the owner of the group?_

In order to transfer the ownership of any group, the first condition is that you must be the owner of the group. In case you are the owner of the group, you can use the `transferGroupOwnership()` method provided by the `CometChat` class.

This will be helpful as the owner is not allowed to leave the group. In case, you as the owner would like to leave the group, you will have to use this method and transfer your ownership first to any other member of the group and only then you will be allowed to leave the group.

```java
String GUID = "supergroup";
String UID = "superhero2";

CometChat.transferGroupOwnership(GUID, UID, new CometChat.CallbackListener<String>() {
  @Override
  public void onSuccess(String s) {
    Log.e(TAG, "Transfer group ownership successful");
  }

  @Override
  public void onError(CometChatException e) {
    Log.e(TAG, "Transfer group ownership failed : " + e.getMessage());
  }

});
```

```kotlin
val GUID = "supergroup"
val UID = "superhero2"

CometChat.transferGroupOwnership(GUID, UID, object : CallbackListener<String?>() {
  override fun onSuccess(s: String?) {
    Log.e(TAG, "Transfer group ownership successful")
  }

  override fun onError(e: CometChatException) {
    Log.e(TAG, "Transfer group ownership failed : " + e.message)
  }
})
```

