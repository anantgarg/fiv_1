When a user logs into your app, you need to programmatically login the user into CometChat. But before you log in the user to CometChat, you need to create the user.

Summing up-

**When a user registers in your app**

1. You add the user details in your database
2. You create a user in CometChat

**When a user logs into your app**

1. You log in the user to your app
2. You [log in the user to CometChat](https://www.cometchat.com/docs/v3/android-chat-sdk/authentication) (programmatically)

## Creating a user

Ideally, user creation should take place at your backend. You can refer our Rest API to learn more about [creating a user](https://www.cometchat.com/docs/v3/chat-apis#createuser) and use the appropriate code sample based on your backend language.

However, if you wish to create users on the fly, you can use the `createUser()` method. This method takes a `User` object and the `API Key` as input parameters and returns the created `User` object if the request is successful.

For more details on the fields present in the User class, please check [this](https://www.cometchat.com/docs/v3/android-chat-sdk/users-user-management#user-class)

```java
String apiKey = "AUTH_KEY"; __ Replace with your API Key.
User user = new User();
user.setUid("user1"); __ Replace with your uid for the user to be created.
user.setName("Kevin"); __ Replace with the name of the user

CometChat.createUser(user, apiKey, new CometChat.CallbackListener<User>() {
  @Override
  public void onSuccess(User user) {
    Log.d("createUser", user.toString());
  }

  @Override
  public void onError(CometChatException e) {
    Log.e("createUser", e.getMessage());
  }
});
```

```kotlin
val apiKey = "API_KEY" __ Replace with your API Key.
val user = User()
user.uid = "user1" __ Replace with your uid for the user to be created.
user.name = "Kevin" __ Replace with the name of the user

CometChat.createUser(user, apiKey, object : CometChat.CallbackListener<User>() {
  override fun onSuccess(user: User) {
    Log.d("createUser", user.toString())
  }

  override fun onError(e: CometChatException) {
    Log.e("createUser", e.message)
  }
})
```



> UID can be alphanumeric with underscore and hyphen. Spaces, punctuation and other special characters are not allowed.

## Updating a user

Updating a user similar to creating a user should ideally be achieved at your backend using the Restful APIs. For more information, you can check the [update a user](https://www.cometchat.com/docs/v3/chat-apis#updateuser) section. However, this can be achieved on the fly as well using the `updateUser()` method. This method takes a `User` object and the API Key as inputs and returns the updated `User` object on successful execution of the request.

```java
String apiKey = "AUTH_KEY"; __ Replace with your API Key.
User user = new User();
user.setUid("user1"); __ Replace with your uid for the user to be updated.
user.setName("Kevin Fernandez"); __ Replace with the name of the user

CometChat.updateUser(user, apiKey, new CometChat.CallbackListener<User>() {
  @Override
  public void onSuccess(User user) {
    Log.d("updateUser", user.toString());
  }

  @Override
  public void onError(CometChatException e) {
    Log.e("updateUser", e.getMessage());
  }
});
```

```kotlin
val apiKey = "API_KEY" __ Replace with your API Key.
val user = User()
user.uid = "user1" __ Replace with your uid for the user to be updated.
user.name = "Kevin Fernandez" __ Replace with the name of the user

CometChat.updateUser(user, apiKey, object : CometChat.CallbackListener<User>() {
  override fun onSuccess(user: User) {
    Log.d("updateUser", user.toString())
  }

  override fun onError(e: CometChatException) {
    Log.e("updateUser", e.message)
  }
})
```



Please make sure the `User` object provided to the `updateUser()` method has the `UID` of the user to be updated set.

## Updating logged-in user

Updating a logged-in user is similar to updating a user. The only difference being this method does not require an AuthKey. This method takes a `User` object as input and returns the updated `User` object on the successful execution of the request.

```java
User user = new User();
user.setName("Iron Man"); 

CometChat.updateCurrentUserDetails(user, new CometChat.CallbackListener<User>() {
  @Override
  public void onSuccess(User user) {
    Log.d(TAG, user.toString());
  }

  @Override
  public void onError(CometChatException e) {
    Log.d(TAG, e.getMessage());
  }
});
```

```kotlin
val user = User()
user.name = "Iron Man"

CometChat.updateCurrentUserDetails(user, object : CallbackListener<User>() {
  override fun onSuccess(user: User) {
    Log.d(TAG, user.toString())
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, e.message)
  }
})
```



By using the `updateCurrentUserDetails()` method one can only update the logged-in user irrespective of the UID passed. Also, it is not possible to update the role of a logged-in user.

## Deleting a user

Deleting a user can only be achieved via the Restful APIs. For more information please check the [delete a user ](https://www.cometchat.com/docs/v3/chat-apis#deleteuser)section.

## User Class

| Field | Editable | Information | 
| ---- | ---- | ---- | 
| uid | specified on user creation. Not editable after that | Unique identifier of the user | 
| name | Yes | Display name of the user | 
| avatar | Yes | URL to profile picture of the user | 
| link | Yes | URL to profile page | 
| role | Yes | User role of the user for role based access control | 
| metadata | Yes | Additional information about the user as JSON | 
| status | No | Status of the user. Could be either online/offline | 
| statusMessage | Yes | Any custom status message that needs to be set for a user | 
| lastActiveAt | No | The unix timestamp of the time the user was last active. | 
| hasBlockedMe | No | A boolean that determines if the user has blocked the logged in user | 
| blockedByMe | No | A boolean that determines if the logged in user has blocked the user | 
| tags | Yes | A list of tags to identify specific users | 
