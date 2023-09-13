User can modify badge count properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify badge count properties.

User can achieve badge count configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| width | Modify width of the badge count using this configuration | 
| height | Modify height of the badge count using this configuration | 
| borderWidth | Modify border width of the badge count using this configuration | 
| borderColor | Modify border color of the badge count using this configuration | 
| cornerRadius | Modify border radius of the badge count using this configuration | 


---

## Step 1: Create BadgeCountConfiguration Object.

```swift
let badgeCountConfiguration = new BadgeCountConfiguration();
badgeCountConfiguration.cornerRadius = "10px";
```



## Step 2: Provide it to Configurations in the particular module

```swift
<CometChatConversations 
    title="Recent Chats" 
    conversationType="both"
    configurations={badgeCountConfiguration}
_>
```

