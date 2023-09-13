This component is of class `UIImageView` and is customizable to display `CometChatMessageReceipt`.

![](https://res.cloudinary.com/developerhub/image/upload/v1644932186/v2_5163/faqapinahm30htlbflhn.png)

---

## Methods

### Progress Icon

This method is used to set  Progress Icon for Message Receipt.

|  |  | 
| ---- | ---- | 
| `set(messageInProgressIcon: UIImage)` | Used to set In Progress Icon for Message Receipt. | 


```swift
__ Syntax for  set(messageInProgressIcon: UIImage)
messageReceipt.set(messageInProgressIcon: "progress-icon.png")
```



---

### Sent Icon

This method is used to set  sent Icon for Message Receipt.

|  |  | 
| ---- | ---- | 
| `set(messageSentIcon: UIImage)\n\n` | Used to set In sent Icon for Message Receipt. | 


```swift
__ Syntax for  set(messageSentIcon: UIImage)
messageReceipt.set(messageSentIcon: "sent-icon.png")
```



---

### Delivered Icon

This method is used to set  delivered Icon for Message Receipt

|  |  | 
| ---- | ---- | 
| `set(messageDeliveredIcon: UIImage)\n\n` | Used to set In delivered Icon for Message Receipt. | 


```swift
__ Syntax for  set(messageDeliveredIcon: UIImage)
messageReceipt.set(messageDeliveredIcon: "delivered-icon.png")
```



---

### Read Icon

This method is used to set  read Icon for Message Receipt

|  |  | 
| ---- | ---- | 
| `set(messageReadIcon: UIImage)` | Used to set In read Icon for Message Receipt. | 


```swift
__ Syntax for  set(messageReadIcon: UIImage)
messageReceipt.set(messageReadIcon: "read-icon.png")
```



---

### Error Icon

This method is used to set error Icon for Message Receipt

|  |  | 
| ---- | ---- | 
| `set(messageErrorIcon: UIImage)` | This method is used to set error Icon for Message Receipt | 


```swift
__ Syntax for  set(messageErrorIcon: UIImage)
messageReceipt.set(messageErrorIcon: "error-icon.png")
```



---

### Receipt

This method is used to set receipt for Message Receipt using SDK's `BaseMessage` Object. 

|  |  | 
| ---- | ---- | 
| `set(receipt forMessage: BaseMessage)` | This method is used to set receipt for Message Receipt using SDK's `BaseMessage` Object. | 


```swift
__ Syntax for  set(receipt forMessage: BaseMessage)
messageReceipt.set(receipt forMessage: message)
```

