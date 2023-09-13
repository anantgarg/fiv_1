User can modify convesation list properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify conversation list properties.

User can achieve conversation list configuration as follows:

| Configuration | Description | 
| ---- | ---- | 
| background | Modify background of the conversation list using this configuration | 
| conversationListItemConfiguration | Modify conversationListItem  in the conversation list using this configuration | 


---

## Step 1: Create ConversationListConfiguration Object.

```javascript
const avatarConfiguration = new AvatarConfiguration();
avatarConfiguration.width = "48px";
avatarConfiguration.height = "48px";
avatarConfiguration.cornerRadius = "8px";

const chatslistitemconfig = new ConversationListItemConfiguration();
chatslistitemconfig.borderWidth = "5px";
chatslistitemconfig.borderStyle = "dotted";
chatslistitemconfig.background = "green";

const listconfig = {
  conversationListItemConfiguration: chatslistitemconfig,
  avatarConfiguration: avatarConfiguration,
};
```



## Step 2: Provide it to Configurations in the particular module

```javascript
<CometChatConversationsList
     configurations={listconfig}
_>
```

