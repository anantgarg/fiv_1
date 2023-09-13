You can modify the `BadgeCount` component's properties using the `BadgeCountConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `BadgeCountConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(cornerRadius: CGFloat)` | Modify corner radius of the `BadgeCount` | 


---

## Step 1: Create BadgeCountConfiguration Object.

```swift
let badgeCountConfiguration = BadgeCountConfiguration().set(cornerRadius: 10)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [badgeCountConfiguration])
```

