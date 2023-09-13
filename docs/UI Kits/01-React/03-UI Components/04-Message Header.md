`CometChatMessageHeader` displays the `User` or `Group` information using SDK's `User` or `Group object.` It also shows the typing indicator when the other user starts typing in `MessageComposer`.

![](https://res.cloudinary.com/developerhub/image/upload/v1645713576/v2_5163/uehbpvdgvzf4otrquscd.png)

![](https://res.cloudinary.com/developerhub/image/upload/v1645713565/v2_5163/addfxqu8qzp2oufq7bod.png)

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

