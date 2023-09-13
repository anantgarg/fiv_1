`CometChatConversationsWithMessages` is a wrapper component which provides functionality to open the `CometChatMessages` widget with a tap of any conversation shown in the list of conversations.

It has the same behaviour as [CometChatConversations](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations) does, but [CometChatMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/messages) is integrated within it. So you don't need to add any code snippet to handle on tap gesture on any conversation item.

### Usage

`CometChatConversationsWithMessages` can be launched by adding the following code snippet into the XML layout file.

![](https://uploads.developerhub.io/prod/x9W8/ue7i3xnfyfd3a5nyxntynzk0pfylhntrurzazqlkoocvhx6scs46ncs7pa4rkk8d.png)

## Usage

`CometChatConversationsWithMessages` can be launched by adding the following code snippet into XML layout file.

```xml
<com.cometchat.chatuikit.conversationswithmessages.CometChatConversationsWithMessages
        android:id="@+id_conversation"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



#### Usage in Fragment and Activity Class

```java
__for Fragment class
 @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
       return new CometChatConversationsWithMessages(getContext());
    }

__for Activity class
 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       setContentView(new CometChatConversationsWithMessages(this));
    }
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setConversationsConfiguration** | [ConversationsConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations-configuration) | used to configure [CometChatConversations](https://www.cometchat.com/docs/v3/android-v4-uikit/conversations) component | 
| **setMessageConfiguration** | [MessagesConfiguration](https://www.cometchat.com/docs/v3/java-chat-ui-kit/cometchatmessagesconfiguration) | used to configure   [CometChatMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/messages) component | 
| **setStartConversationConfiguration** | [ContactsConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/contacts-configuration) | Used to configure [CometChatContacts](https://www.cometchat.com/docs/v3/android-v4-uikit/contacts) component. | 
| **setUser** | User | used to automatically to navigate to the CometChatMessages component for the passed User while the process for fetching conversations continues in the background | 
| **setGroup** | Group | used to automatically to navigate to the CometChatMessages component for the passed Group while the process for fetching conversations continues in the background | 
