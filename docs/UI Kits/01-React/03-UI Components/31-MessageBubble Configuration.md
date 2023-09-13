User can modify message bubbles properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify all types of bubble properties.

User can achieve message bubble configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| `set(avatarConfiguration:AvatarConfiguration)` | Modify avatar in the message bubble using this configuration | 


---

## Step 1: Create MessageBubble Object.

```swift
let messageBubbleConfiguration = MessageBubbleConfiguration();
messageBubbleConfiguration.background = "#c4c4c4";
```



## Step 2: Provide it to Configurations in the particular module

```swift
<CometChatMessages 
    group={{guid: "supergroup"}} 
  	liveReaction="❤️" 
		hideEmoji="false"
		configurations={messageBubbleConfiguration}
_>
```

