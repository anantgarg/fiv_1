You can modify the `GroupListItem` component's properties using the `GroupListItemConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `GroupListItemConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(background: [CGColor])` | Modify the background of group list item | 
| `set(avatarConfiguration: AvatarConfiguration)` | Modify the avatar present in  group list item | 
| `set(statusIndicatorConfiguration: StatusIndicatorConfiguration)` | Modify the status indicator present in  group list item | 
| `hide(statusIndicator: Bool)` | Hide status indicator present in group list item | 
| `hide(avatar: Bool)` | Hide avatar present in group list item | 
| `set(inputData: InputData)` | This will set the data for group list item | 


## Step 1: Create GroupListItemConfiguration Object.

```swift
let avatarConfiguration = AvatarConfiguration().set(borderWidth: 2).set(cornerRadius: 15)
let badgeCountConfiguration = BadgeCountConfiguration().set(cornerRadius: 10)
let statusIndicatorConfiguration = 
StatusIndicatorConfiguration().set(cornerRadius: 12)
															.set(borderWidth: 2)
														  
__ Creating `ConversationListItemConfiguration` Object

let groupListItemConfiguration = 
groupListItemConfiguration().set(avatarConfiguration: avatarConfiguration)
																	 .set(statusIndicatorConfiguration: statusIndicatorConfiguration)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [groupListItemConfiguration])
```

