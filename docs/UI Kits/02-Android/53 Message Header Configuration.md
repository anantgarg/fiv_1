You can modify the [CometChatMessageHeader](https://www.cometchat.com/docs/v3/android-v4-uikit/message-header) component's properties using the `MessageHeaderConfiguration` object when using its parent components . To use a configuration, you simply need to pass it to the parent component.

The `MessageHeaderConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setBackIconView** | View | used to set back button widget | 
| **setSubtitle** | Function3&lt;Context, User, Group, View&gt; | Used to set custom subtitle view | 
| **setListItemView** | Function3&lt;Context, User, Group, View&gt; | used to set custom list item view | 
| **disableUsersPresence** | boolean | used to toggle functionality to show user's presence | 
| **setProtectedGroupIcon** | @DrawableRes\n\nint | used to set protected group icon | 
| **setPrivateGroupIcon** | @DrawableRes\n\nint | used to set private group icon | 
| **setStyle** | MessageHeaderStyle | used to set styling properties for message header | 
| **hideBackIcon** | boolean | used to toggle back button visibility | 
| **setMenu** | Function3&lt;Context, User, Group, View&gt; | used to add options in app bar | 


## Step 1: Create MessageHeaderConfiguration Object.

for instance you want to hide back button from message header 

```java
MessageHeaderConfiguration configuration = new MessageHeaderConfiguration().hideBackIcon(true);
```



## Step 2: Provide it to Configurations in the particular module

```java
cometChatMessages.setMessageHeaderConfiguration(configuration);
```

