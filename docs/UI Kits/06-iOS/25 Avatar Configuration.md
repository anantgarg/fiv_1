You can modify the Avatar component's properties using the `AvatarConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `AvatarConfiguration`  supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `set(cornerRadius: CGFloat)` | Modify corner radius of the Avatar | 
| `set(borderWidth: CGFloat)` | Modify border width of the Avatar | 
| `set(outerViewWidth: CGFloat)` | Modify outer width of the Avatar | 
| `set(outerViewSpacing: CGFloat)` | Modify border outerView spacing of the Avatar | 


---

## Step 1: Create AvatarConfiguration Object.

```swift
let avatarConfiguration = AvatarConfiguration().set(borderWidth: 2).set(cornerRadius: 15)
```



## Step 2: Provide it to Configurations in the particular module

```swift
self.set(configurations: [avatarConfiguration])
```

