**UI Components** are building blocks of the UI Kit. **UI Components** are a set of custom classes specially designed to build a rich chat app. There are different UI Components available in the
UI Kit Library. 

## CometChatUI

**CometChatUI** is an option to launch a fully functional chat application using the UI Kit. In **CometChatUI**  all the **UI Components** are interlinked and work together to launch a fully functional chat on your website/application

![CometChatUI  component](https://res.cloudinary.com/developerhub/image/upload/v1623200231/v2_5163/wvil8hjtvpqcgx6zik9e.png)

```javascript
import { CometChatUI } from ".._components_CometChatUI_CometChat_cometchat-ui.module";

<div>
  <CometChatUI><_CometChatUI>
<_div>
```



## CometChatUserListWithMessages

The `CometChatUserListWithMessages` is a component with a list of users. The component has all the necessary listeners and methods required to display the user's list and shows the set of the messages/chats of the selected user

![CometChatUserListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200239/v2_5163/qmi9vkix1qmkzqporpfz.png)

```javascript
import { CometChatUserListWithMessages } from ".._components_Users_CometChat-user-list-with-messages_cometchat-user-list-with-messages.module";

<div>
  <cometchat-user-list-with-messages><_cometchat-user-list-with-messages>
<_div>
```



## CometChatGroupListWithMessages

The `CometChatGroupListWithMessages` is a component with a list of groups. The component has all the necessary listeners and methods required to display the group's list and shows the set of the messages/chats of the selected group

![CometChatGroupListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200243/v2_5163/olppnkt9a62lmlfbzkie.png)

```javascript
import { CometChatGroupListWithMessages } from ".._components_Groups_CometChat-group-with-messages_cometchat-group-list-with-messages.module";
<div>
  <cometchat-group-list-with-messages><_cometchat-group-list-with-messages>
<_div>
```



## CometChatConversationListWithMessages

The `CometChatConversationListWithMessages` is a component with a list of recent conversations. The component has all the necessary listeners and methods required to display the recent conversation list and shows the set of the messages/chats of the selected recent conversation

![CometChatConversationListWithMessages component](https://res.cloudinary.com/developerhub/image/upload/v1623200248/v2_5163/fq9rmcd2khvyccqa97ux.png)

```javascript
import { CometChatConversationListWithMessages } from ".._components_Chats_CometChat-conversation-list-with-messages_cometchat-conversation-list-with-messages.module";
<div>
  <cometchat-conversation-list-with-messages><_cometchat-conversation-list-with-messages>
<_div>
```



## CometChatMessages

The `CometChatMessages` is a component with a list of messages/chats and shows the message component header and message composer.

```typescript
import { CometChatMessages } from ".._components_Messages_CometChat-messages_cometchat-messages.module";
<div>
  <cometchat-messages><_cometchat-messages>
<_div>
```



## CometChatUserList

The `CometChatUserList` is a component that displays the list of users available to chat. You can use this component within your app if you wish to display the list of users.

![CometChatUserList component](https://res.cloudinary.com/developerhub/image/upload/v1623200254/v2_5163/b9kihl712xl0olig5xzn.png)

```javascript
import { CometChatUserList } from ".._components_Users_CometChat-user-list_cometchat-user-list.module";
<div>
  <cometchat-user-list [friendsOnly]=true> <_cometchat-user-list>
<_div>
```



| Parameter | Description | Type | 
| ---- | ---- | ---- | 
| friendsOnly | This property when set to true will return only the friends of the logged-in user.\nValue could be _true_ or _false_ | Optional | 


## CometChatGroupList

The `CometChatGroupList` is a component that displays the list of groups available. You can use this component within your app if you wish to display the list of groups.

![CometChatGroupList component](https://res.cloudinary.com/developerhub/image/upload/v1623200257/v2_5163/qdztfbzeountllfbhcwl.png)

```javascript
import { CometChatGroupList } from ".._components_Groups_CometChat-group-list_cometchat-group-list.module";
<div>
  <cometchat-group-list><_cometchat-group-list>
<_div>
```



## CometChatConversationList

You can use the `CometChatConversationList` component to display the list of recent conversations that the logged-in user was a part of.

![CometChatConversationList component](https://res.cloudinary.com/developerhub/image/upload/v1623200260/v2_5163/u87hri0tjgfftxdp2vvv.png)

```javascript
import { CometChatConversationList } from ".._components_Chats_CometChat-conversation-list_cometchat-conversation-list.module";
<div>
  <cometchat-conversation-list><_cometchat-conversation-list>
<_div>
```

