User can modify message composer properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify message composer properties.

User can achieve MessageComposer configuration as follows: 

| Configuration | Description | 
| ---- | ---- | 
| cornerRadius | Modify corner radius of the message composer using this configuration | 
| borderWidth | Modify border width of the message composer using this configuration | 
| width | Modify width of the message composer using this configuration | 
| height | Modify height of the message composer using this configuration | 
| textSize | Modify text size of the message composer using this configuration | 
| maxLines | Modify number of lines of the message composer using this configuration | 
| hideAttachment | Hide attachment icon in the message composer using this configuration | 
| hideMicrophone | Hide microphone in the message composer using this configuration | 
| hideLiveReaction | Hide live reaction button  in the message composer using this configuration | 
| hideSendButton | Hide send button in the message composer using this configuration | 


---

## Step 1: Create MessageComposerConfiguration Object.

```swift
let messageComposerConfiguration = new MessageComposerConfiguration();
messageComposerConfiguration.hideLiveReaction = true;
```



## Step 2: Provide it to Configurations in the particular module

```swift
<CometChatMessages 
    group={{guid: "supergroup"}} 
  	liveReaction="❤️" 
		hideEmoji="false"
		configurations={messageComposerConfiguration}
_>
```

