You can modify the `UserListItem` component's properties using the `UserListItemConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `UserListItemConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(background: [CGColor])` | Modify the background of user list item | 
| `set(inputData: InputData)` | This will set data for user list item | 
| `hide(statusIndicator: Bool)` | Hide status indicator present in user list item | 
| `hide(avatar: Bool)` | Hide avatar present in user list item | 


## Step 1: Create UserListItemConfiguration Object.

```swift
let avatarConfiguration = AvatarConfiguration().set(borderWidth: 2).set(cornerRadius: 15)
let statusIndicatorConfiguration = 
StatusIndicatorConfiguration().set(cornerRadius: 12)
															.set(borderWidth: 2)
														  .set(backgroundColor: .red, forStatus: .offline)
                              .set(backgroundColor: .green, forStatus: .online)

__ Creating `UserListItemConfiguration` Object

let userListItemConfiguration = 
UserListItemConfiguration().set(avatarConfiguration: avatarConfiguration)
													.set(statusIndicatorConfiguration: statusIndicatorConfiguration)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [userListItemConfiguration])
```

