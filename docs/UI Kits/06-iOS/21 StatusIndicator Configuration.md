You can modify the `StatusIndicator` component's properties using the `StatusIndicatorConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `StatusIndicatorConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(cornerRadius: CGFloat)` | Modify the corner radius of the status indicator | 
| `set(borderWidth: CGFloat)` | Modify the border width of the status indicator | 
| `set(backgroundColor: UIColor, forStatus: CometChat.UserStatus)` | Modify the background color for user status | 


---

## Step 1: Create StatusIndicatorConfiguration Object.

```swift
let statusIndicatorConfiguration = StatusIndicatorConfiguration()
																		.set(cornerRadius: 12)
																		.set(borderWidth: 2)
																		.set(backgroundColor: .red, forStatus: .offline)
																		.set(backgroundColor: .green, forStatus: .online)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [statusIndicatorConfiguration])
```

