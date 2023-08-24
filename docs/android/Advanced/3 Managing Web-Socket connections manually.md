## Default SDK behaviour on login

When the login method of the SDK is called, the SDK performs the below operations:

1. Logs the user into the SDK
2. Saves the details of the logged in user locally.
3. Creates a web-socket connection for the logged in user.

This makes sure that the logged in user starts receiving real-time messages sent to him or any groups that he is a part of as soon as he logs in.

When the app is reopened, and the init() method is called, the web-socket connection to the server is established automatically.

This is the default behaviour of the CometChat SDKs. However, if you wish to take control of the web-socket connection i.e if you wish to connect and disconnect to the web-socket server manually, you can refer to the Managing Web-socket Connection section.

## Managing the Web-socket connections manually

The CometChat SDK also allows you to modify the above default behaviour of the SDK and take the control of the web-socket connection into your own hands.
In order to achieve this, you need to follow the below steps:

1. While calling the init()  function on the app startup, you need to inform the SDK that you will be managing the web socket connect. You can do so by using the `autoEstablishSocketConnection()`  method provided by the `AppSettingsBuilder` class. This method takes a boolean value as an input. If set to `true` , the SDK will manage the web-socket connection internally based on the default behaviour mentioned above. If set to `false` , the web socket connection can will not be managed by the SDK and you will have to handle it manually. You can refer to the below code snippet for the same:

```java
String appId = "YOUR_APP_ID";
String region = "us";

AppSettings appSettings = new AppSettings.AppSettingsBuilder()
    .setRegion(region)
    .autoEstablishSocketConnection(false)
    .build();

CometChat.init(this, appId, appSettings, new CometChat.CallbackListener<String>() {
    @Override
    public void onSuccess(String s) {
        Log.d(TAG, "Init successful!");
    }

    @Override
    public void onError(CometChatException e) {
        Log.d(TAG, "Error occurred : " + e.getMessage());
    }
});
```

```kotlin
val appId = "YOUR_APP_ID"
val region = "us"

val appSettings = AppSettingsBuilder()
  .setRegion(region)
  .autoEstablishSocketConnection(false)
  .build()

CometChat.init(this, appId, appSettings, object : CallbackListener<String?>() {
  override fun onSuccess(s: String?) {
    Log.d(TAG, "Init successful!")
  }

  override fun onError(e: CometChatException) {
    Log.d(TAG, "Error occurred : " + e.message)
  }
})
```



2. You can manage the connection to the web-socket server using the `connect()`  and `disconnect()`  methods provided by the SDK.
3. Connect to the web-socket server

You need to use the `connect()`  method provided by the `CometChat`  class to establish the connection to the web-socket server. Please make sure that the user is logged in to the SDK before calling this method. You can use the CometChat.getLoggedInUser() method to check this. Once the connection is established, you will start receiving all the real-time events for the logged in user

```java
CometChat.connect();
```

```kotlin
CometChat.connect()
```



2. Disconnect from the web-socket server

You can use the `disconnect()`  method provided by the `CometChat` class to break the established connection. Once the connection is broken, you will stop receiving all the real-time events for the logged in user.

```java
CometChat.disconnect();
```

```kotlin
CometChat.disconnect()
```

