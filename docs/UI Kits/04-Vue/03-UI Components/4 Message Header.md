
`CometChatMessageHeader` displays the `User` or `Group` information using SDK's `User` or `Group object.` It also shows the typing indicator when the other user starts typing in `MessageComposer`.


![](https://uploads.developerhub.io/prod/x9W8/1imt9jhds6lkac1il2vqdmd2j2ahzguo2rfaxsu5147rpc8c1r734cjx08jep6dv.png)



![](https://uploads.developerhub.io/prod/x9W8/ul3oo8odd4ze01kk56591fhoi690zohbp2fujcoll602xbpafg56d6jvamzo2khk.png)


## Properties


| Properties | Description | 
| ---- | ---- | 
| user | Sets the `User` object to fetch user details | 
| group | Sets the `Group` object to fetch group details | 
| background | Sets the background | 
| border | Sets the border | 



## Uses


```javascript
import React from "react";
import {CometChatMessageHeader} from "cometchat-react-ui-kit";

const App = props => {
  return (
  	<CometChatMessageHeader user={{uid: "superhero1"}} background="yellow" _>
  )
}
```




