You can modify the [CometChatCreateGroup](https://www.cometchat.com/docs/v3/android-v4-uikit/create-group) component's properties using the `CreateGroupConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `CreateGroupConfiguration` supports the following configurations:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title | 
| **setCloseIcon** | @DrawableRes\n\nint | used to set back button icon | 
| **setCreateIcon** | @DrawableRes\n\nint | used to set create group icon | 
| **setStyle** | CreateGroupStyle | used to set stying properties | 
| **setNamePlaceHolderText** | String | used to customize the hint text for protected group form's name input field | 
| **setPasswordPlaceHolderText** | String | used to customize the hint text for protected group form's password input field | 
| **setOnCreateGroup** | CometChatCreateGroup.OnCreateGroup | overrides the default functionality triggered on tapping the create group icon | 
| **setOnBackPress** | CometChatListBase.OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when creating group | 


## How to create a CreateGroupConfiguration object and use it ?

please refer the below code snippet to create the object of CreateGroupConfiguration and configure it

```java
CreateGroupConfiguration configuration=new CreateGroupConfiguration().setTitle("Create Group");
```



## Usage

CreateGroupConfiguration can be used in a widget where CometChatCreateGroup is present as a child component. We just pass that `CreateGroupConfiguration` object to that parent widget.

```java
joinProtectedGroup.setCreateGroupConfiguration(configuration);
```

