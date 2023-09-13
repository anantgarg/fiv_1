You can modify the Avatar component's properties using the `AvatarConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `AvatarConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| width | Modify width of the avatar using this configuration | 
| height | Modify height of the avatar using this configuration | 
| cornerRadius | Modify corner radius of the avatar using this configuration | 
| borderWidth | Modify border width of the avatar using this configuration | 
| borderStyle | Modify border style of the avatar using this configuration | 
| outerViewWidth | Modify outer width of the avatar using this configuration | 
| outerViewStyle | Modify outer width style of the avatar using this configuration | 
| outerViewSpacing | Modify outerView spacing of the avatar using this configuration | 


---

## Step 1: Create AvatarConfiguration Object.

```javascript
const avatarConfiguration = new AvatarConfiguration();
  avatarConfiguration.width = "48px";
  avatarConfiguration.height = "48px";
  avatarConfiguration.cornerRadius = "8px";
```



## Step 2: Provide it to Configurations in the particular module

```javascript
<CometChatConversations 
    title="Recent Chats" 
    conversationType="both"
    configurations={avatarConfiguration}
_>
```

