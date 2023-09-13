User can modify messages module  properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify message module properties.

User can achieve messageModule configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| messageHeaderConfiguration | Modify corner radius of the avatar using this configuration | 
| messageListConfiguration | Modify border width of the avatar using this configuration | 
| messageComposerConfiguration | Modify outer width of the avatar using this configuration | 
| background | Modify border outerView spacing of the avatar using this configuration | 


---

## Step 1: Create CometChatMessagesConfiguration Object.

```javascript
const messageHeaderConfiguration = new MessageHeaderConfiguration();
messageHeaderConfiguration.background = "green";

const messageListConfiguration = new MessageListConfiguration();
messageListConfiguration.background = "pink";

const messageComposerConfiguration = new MessageComposerConfiguration();
messageComposerConfiguration.background = "yellow";
messageComposerConfiguration.sendButtonIconURL = sendButtonIcon;

const messagesConfig = {messageHeaderConfiguration, messageListConfiguration, messageComposerConfiguration };
```



## Step 2: Provide it to Configurations in the particular module

```javascript
<CometChatMessages 
    group={{guid: "supergroup"}} 
  	liveReaction="❤️" 
		hideEmoji="false"
		configurations={messagesConfig}
_>
```

