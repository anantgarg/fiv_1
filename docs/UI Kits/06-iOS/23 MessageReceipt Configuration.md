You can modify the `MessageReceipt` component's properties using the `MessageReceiptConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `MessageReceiptConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `setProgressIcon(icon: UIImage)` | Update message progress icon of the message receipt | 
| `setDeliveredIcon(icon: UIImage)` | Update message delivered icon of the message receipt | 
| `setReadIcon(icon: UIImage)` | Update message read icon of the message receipt | 
| `setFailureIcon(icon: UIImage)` | Update message failure icon of the message receipt | 
| `setSentIcon(icon: UIImage)` | Update message sent icon of the message receipt | 


---

## How to create MessageReceiptConfiguration Object and use it ?

#### please refer the below code snippet to create the object of MessageReceiptConfiguration and configure it

```swift
let messageReceiptConfiguration = MessageReceiptConfiguration()

messageReceiptConfiguration.setProgressIcon(icon: UIImage(named: "progress.png"))
                           .setDeliveredIcon(icon: UIImage(named: "delivered.png"))
													 .setReadIcon(icon: UIImage(named: "read.png"))
 													 .setSentIcon(icon: UIImage(named: "sent.png"))
 													 .setFailureIcon(icon: UIImage(named: "error.png"))
```



## Usage

MessageReceiptConfiguration can be use in a module where CometChatMessageList is present as an child component. we can easily set MessageReceiptConfiguration object to the parent component by calling setConfiguration method.

```swift
self.set(configurations: [messageReceiptConfiguration])
```

