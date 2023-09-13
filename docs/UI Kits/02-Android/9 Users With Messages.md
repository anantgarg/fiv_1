`CometChatUsersWithMessages` component integrates the [CometChatUsers](https://www.cometchat.com/docs/v3/android-v4-uikit/users) module with [CometChatMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/messages) module and allows you to navigate to any user's chat window on click of any list item in your user list.

`CometChatUsersWithMessages` contains all the attributes that [CometChatUsers](https://www.cometchat.com/docs/v3/android-v4-uikit/users) provides.

## Usage

`CometChatUsersWithMesasges` can be launched by adding the following code snippet into the XML layout file.

```xml
<com.cometchat.chatuikit.userswithmessages.CometChatUsersWithMessages
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:id="@+id_users_with_messages"
        _>
```



![](https://uploads.developerhub.io/prod/x9W8/a2s8n5226djnjpnqcbfozu1srmy7b0j50u7nh0fg4eloq0l7tbdq1f43zx2fvmrx.png)

### Usage in Fragment and Activity Class

```java
__for Fragment class
 @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
       return new CometChatUsersWithMessages(getContext());
    }

__for Activity class
 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       setContentView(new CometChatUsersWithMessages(this));
    }
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setUsersConfiguration | [UsersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/users-configuration) | used to set User Configuration | 
| setMessagesConfiguration | [MessagesConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/messages-configuration) | used to set Message Configuration | 
| setUser | User | used to navigate to the CometChatMessages component for a specific users while fetching process for users can continue in the background | 
