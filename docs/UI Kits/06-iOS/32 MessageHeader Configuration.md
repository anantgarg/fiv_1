You can modify the MessageHeader component's properties using the MessageHeaderConfiguration object. To use a configuration, you simply need to pass it to the parent component.

The MessageHeaderConfiguration supports the following properties:

|  |  | 
| ---- | ---- | 
| `set(avatarConfiguration: AvatarConfiguration)` | This method is use to control the properties of the avatar used in MessageHeader | 
| `set(statusIndicatorConfiguration: StatusIndicatorConfiguration)` | This method is use to control the properties of the status indicator used in MessageHeader | 
| `set(inputData: InputData)` | This method is use to control the Visibility of the avatar, title, subtitle, status indicator and can also change the data of subtitle as per the user input. | 
| hide(backButton: Bool) | This method is use to hide back button used in MessageHeader | 
| hide(videoCall: Bool) | This method is use to hide video call button used in MessageHeader | 
| hide(audioCall: Bool) | This method is use to hide audio button used in MessageHeader | 
| hide(info: Bool) | This method is use to hide info button used in MessageHeader | 


## How to create MessageHeaderConfiguration Object and use it ?

#### please refer the below code snippet to create the object of MessageHeaderConfiguration and configure it

```swift
__ if you want to change the subtitle of DataItem in user List using `User` object.
var inputData = InputData(title: true, thumbnail: true, status: true) { user in
       return (user as? User)?.metadata?["address"] as? String ?? "" 
       __ you can use any field from the user object to display the information in user list
       } 

 
__ if you want to change the subtitle of DataItem in group List using `Group` object.
var inputData = InputData(title: true, thumbnail: true, status: true) { group in
       return (group as? Group)?.description ?? "" 
       __ you can use any field from the group object to display the information in user list
       } 

___ if you want to change the subtitle of DataItem in group member List using `GroupMember` object.
var inputData = InputData(title: true, thumbnail: true, status: true) { groupMember in
       return (groupMember as? GroupMember)?.metadata?["stars"] as? String ?? "" 
       __ you can use any field from the group object to display the information in user list
       } 

__creating object of MessageHeaderConfiguration
var messageHeaderConfiguration = MessageHeaderConfiguration()

__creating object of AvatarConfiguration
let avatarConfiguration = AvatarConfiguration().set(cornerRadius: 10)

__set input data into configuration
messageHeaderConfiguration.set(inputData: inputData)
messageHeaderConfiguration.hide(audioCall: true)
```



## Usage

MessageHeaderConfiguration can be use in a module where CometChatMessageHeader is present as an child component. we can easily set MessageHeaderConfiguration object to the parent component by calling setConfiguration method.

```swift
self.set(configurations: [messageHeaderConfiguration])
```

