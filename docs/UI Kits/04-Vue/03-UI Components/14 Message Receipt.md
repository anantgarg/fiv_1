
`CometChatMessageReceipt` component renders the status (read receipts, pending state indicator etc.) of a message.


![](https://uploads.developerhub.io/prod/x9W8/pzvxvfofjdfep5k3d7an7bc5c99tj44kuda3zzyqewo16cbfg0avdsqb2hmyxfsp.png)


---

## Properties


| Props | Description | 
| ---- | ---- | 
| `messageWaitIcon` | Sets icon when the message is _**being sent**_ | 
| `messageSentIcon` | Sets icon when the message status is _**sent**_ | 
| `messageDeliveredIcon` | Sets icon when the message status is **_delivered_** | 
| `messageReadIcon` | Sets icon when the message status is _**read**_ | 
| `messageErrorIcon` | Sets icon when the message sent has encountered an _**error**_ | 



---

## Uses


```javascript
import React from "react";
import { CometChatMessageReceipt } from "cometchat-react-ui-kit";
import messageReadIcon from "._assets_read.svg";

const App = props => {
  
  const messageObject = CometChat SDK's message object;
	return (
    <CometChatMessageReceipt messageObject={messageObject} messageReadIcon={messageReadIcon} _>
  ) 
}
```




