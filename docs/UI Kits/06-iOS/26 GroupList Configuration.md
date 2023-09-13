You can modify the `GroupList` component's properties using the `GroupListConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

| Configuration | Description | 
| ---- | ---- | 
| `set(emptyView: UIView)` | This will show the empty view when the list is empty | 
| `hide(error: Bool)` | If set to true, it will hide error Ui from the screen. | 
| `set(joinedOnly: Bool)` | If set to true then only Joined group will be fetched. | 
| `set(searchKeyword: String)` | This method is used to fetch user List in to `CometChatGroupList` based on keyword provided. | 
| `set(tags: [String])` | This will fetch filtered list in to CometChatGroupList based on given array of String. | 
| `set(limit: Int)` | This will set the number of group to be fetched in one go. | 
| `set(errorText: String?)` | This will load the user defined text , when any error occurs. | 
| `set(emptyText: String?)` | This will load the user defined text , when list is empty. | 


## How to create GroupListConfiguration Object and use it ?

#### please refer the below code snippet to create the object of GroupListConfiguration and configure it.

```swift
var tags: [String] = [String]()

__ Creating `GroupListConfiguration` Object

 let groupListConfiguration = GroupListConfiguration()
                                   
groupsListConfiguration.set(searchKeyword: "Searched Text")	
                .hide(error: false)
                .set(joinedOnly: false)
                .set(limit:30)
                .set(tags: tags)
                .set(emptyView: nil)
								.set(errorText: "Something went wrong!")
								.set(emptyText: "empty list")
```



#### Usage

GroupsListConfiguration can be use in a module where CometChatGroupList is present as an child component. we can easily set `GroupsListConfiguration` object to the parent component by calling setConfiguration method.

```swift
set(configurations: [groupsListConfiguration])
```

