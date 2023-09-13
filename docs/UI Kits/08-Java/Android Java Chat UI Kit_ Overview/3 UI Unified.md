
![](https://res.cloudinary.com/developerhub/image/upload/v1623200137/v2_5163/llmautkhddwpsdm2rhyn.png)

You can launch `UI Unified` after a successful login using CometChat.To use Unified UI you have to launch `CometChatUnified`  Activity. Make sure to add the following code snippet in `onSuccess` of CometChat login.

```java
startActivity(new Intent(YourActivity.this,CometChatUnified.class))
```


