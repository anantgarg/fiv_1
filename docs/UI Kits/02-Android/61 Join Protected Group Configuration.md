You can modify the [CometChatJoinProtectedGroup](https://www.cometchat.com/docs/v3/android-v4-uikit/join-protected-group) component's properties using the `JoinProtectedGroupConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `JoinProtectedGroupConfiguration` supports the following properties:

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setTitle** | String | used to set title | 
| **setDescription** | String | used to set description | 
| **setPlaceHolderText** | String | used to customize the hint text for the form's password input field | 
| **setCloseIcon** | @DrawableRes\n\nint | used to set back button icon | 
| **setOnJoinClick** | CometChatJoinProtectedGroup.OnJoinClick | used to override the default functionality triggered on join group icon tap | 
| **setJoinIcon** | @DrawableRes\n\nint | Used to set joinIcon button | 
| **setStyle** | JoinProtectedGroupStyle | Used to set styling properties | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when joining group | 
| **setOnBackPress** | CometChatListBase.OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 


## How to create a JoinProtectedGroupConfiguration object and use it ?

please refer the below code snippet to create the object of JoinProtectedGroupConfiguration and configure it

```java
JoinProtectedGroupConfiguration joinProtectedGroupConfiguration=new JoinProtectedGroupConfiguration().setTitle("Join");
```



## Usage

`JoinProtectedGroupConfiguration` can be used in a widget where `CometChatJoinProtectedGroup` is present as a child component. We just pass that `JoinProtectedGroupConfiguration` object to that parent widget.

```java
joinProtectedGroup.setJoinGroupConfiguration(joinProtectedGroupConfiguration);
```

