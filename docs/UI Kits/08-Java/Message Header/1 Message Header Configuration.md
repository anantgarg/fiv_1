You can modify the `CometChatMessageHeader` component's properties using the `MessageHeaderConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageHeaderConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| setBackIcon(Drawable icon) | Modify back icon using this configuration | 
| setAudioCallIcon(Drawable icon) | Modify audio call icon using this configuration | 
| setVideoCallIcon(Drawable icon) | Modify video call icon using this configuration | 
| setInfoIcon(Drawable icon) | Modify info icon using this configuration | 
| setAvatarConfiguration(AvatarConfiguration avatarConfig) | Modify Avatar component of CometChatMessageHeader using this component | 
| setStatusIndicatorConfiguration(StatusIndicatorConfiguration config) | Modify StatusIndicator component of CometChatMessageHeader using this component. | 


## Step 1: Create MessageHeaderConfiguration Object.

```java
AvatarConfiguration avatarConfig = new AvatarConfiguration(context);
avatarConfig.setCornerRadius(12);
avatarConfig.setBorderWidth(4);

MessageHeaderConfiguration headerConfiguration = new CometChatHeaderConfiguration(context);
headerConfiguration.hideInfo(true);
headerConfiguration.setVideoCallIcon(getResources().getDrawable(R.drawable.video_slack));
headerConfiguration.setAvatarConfiguration(avatarConfig);
```



## Step 2: Provide it to Configurations in the particular module

```java
setConfiguration(headerConfiguration);
```

