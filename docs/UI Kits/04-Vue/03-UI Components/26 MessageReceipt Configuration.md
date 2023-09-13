
User can modify message receipt properties using Configurations. Configurations are helpful where user can pass this particular configuration to parent component to modify message receipt properties.

User can achieve MessageReceipt configuration as follows:


| Configuration | Description | 
| ---- | ---- | 
| messageWaitIcon | Update message wait icon of the message receipt using this configuration | 
| messageSentIcon | Update message sent icon of the message receipt using this configuration | 
| messageDeliveredIcon | Update message delivered icon of the message receipt using this configuration | 
| messageReadIcon | Update message read icon of the message receipt using this configuration | 
| messageErrorIcon | Update message error icon of the message receipt using this configuration | 


---

## Step 1: Create MessageReceiptConfiguration Object.


```javascript
let messageReceiptConfiguration = new MessageReceiptConfiguration();
messageReceiptConfiguration.deliveredIcon = "read-updated.png";
```




## Step 2: Provide it to Configurations in the particular module


```javascript
<CometChatConversationsListItem
     configurations={messageReceiptConfiguration}
_>
```




