
User can modify message list properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify message list properties.

User can achieve message list configuration as follows:


| Configuration | Description | 
| ---- | ---- | 
| background | Modify background of the message list using this configuration | 


---

## Step 1: Create MessageList Object.


```javascript
let messageListConfiguration = MessageListConfiguration();
messageListConfiguration.background = "#c4c4c4";
```




## Step 2: Provide it to Configurations in the particular module


```javascript
<CometChatMessages 
    group={{guid: "supergroup"}} 
  	liveReaction="❤️" 
		hideEmoji="false"
		configurations={messageListConfiguration}
_>
```




