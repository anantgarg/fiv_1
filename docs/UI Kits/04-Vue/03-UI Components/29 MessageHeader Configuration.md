
User can modify message header properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify message header properties.

User can achieve message header configuration as follows:


| Configuration | Description | 
| ---- | ---- | 
| background | Modify the background color | 
| avatarConfiguration | Modify avatar  using this configuration | 
| statusIndicatorConfiguration | Modify status indicator  using this configuration | 


---

## Step 1: Create MessageHeaderConfiguration Object.


```swift
let messageHeaderConfiguration = new MessageHeaderConfiguration();
messageHeaderConfiguration.background = "#f7f7f7";
```




## Step 2: Provide it to Configurations in the particular module


```swift
<CometChatMessages 
    group={{guid: "supergroup"}} 
  	liveReaction="❤️" 
		hideEmoji="false"
		configurations={messageHeaderConfiguration}
_>
```




