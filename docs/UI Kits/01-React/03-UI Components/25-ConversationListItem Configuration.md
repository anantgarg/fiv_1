User can modify conversationListItem properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify avatar properties.

User can achieve avatar configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| avatarConfiguration | Modify avatar present in  conversation list item using this configuration | 
| statusIndicatorConfiguration | Modify status indicator present in  conversation list item using this configuration | 
| badgeCountConfiguration | Modify badge count present in  conversation list item using this configuration | 
| messageReceiptConfiguration | Modify message receipt present in conversation list item using this configuration | 


---

## Step 1: Create ConversationListItemConfiguration Object.

```swift
const avatarConfiguration = new AvatarConfiguration();
avatarConfiguration.width = "48px";
avatarConfiguration.height = "48px";
avatarConfiguration.cornerRadius = "8px";

const badgeCountConfig = new BadgeCountConfiguration();
badgeCountConfig.cornerRadius = "5px";

const listItemconfig = {
  badgeCountConfiguration: badgeCountConfig,
  avatarConfiguration: avatarConfiguration,
};
```



## Step 2: Provide it to Configurations in the particular module

```swift
<CometChatConversationsListItem
     configurations={listItemConfig}
_>
```

