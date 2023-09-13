User can modify status indicator properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify status indicator properties.

User can achieve status indicator configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| width | Modify width of the status indicator using this configuration | 
| height | Modify height of the status indicator using this configuration | 
| border | Modify border of the status indicator using this configuration | 
| cornerRadius | Modify corner radius of the status indicator using this configuration | 
| onlineBackgroundColor | Modify background color for online status of the status indicator using this configuration | 
| offlineBackgroundColor | Modify background color for offline status of the status indicator using this configuration | 
| style | Modify style attribute of the status indicator using this configuration | 


---

## Step 1: Create StatusIndicatorConfiguration Object.

```swift
let statusIndicatorConfiguration = StatusIndicatorConfiguration();
statusIndicatorConfiguration.border = "2px solid white";
```



## Step 2: Provide it to Configurations in the particular module

```swift
<CometChatConversations 
    title="Recent Chats" 
    conversationType="both"
    configurations={statusIndicatorConfiguration}
_>
```

