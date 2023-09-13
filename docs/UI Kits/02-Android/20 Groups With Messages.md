`CometChatGroupsWithMessages` is a wrapper component which provide functionality to open `CometChatMessages` module on a click of any group shown in group list.

It has the Same behaviour as [CometChatGroups](https://www.cometchat.com/docs/v3/android-v4-uikit/groups) does.

![](https://uploads.developerhub.io/prod/x9W8/b23vtrbh6js9nfor04uqu0buc90z8f942od7tlsmbpe2p8p067dc8emugxjwxqrt.png)

### Usage

`CometChatGroupsWithMessages` can be launched by adding the following code snippet into XML layout file.

```xml
<com.cometchat.chatuikit.groupswithmessages.CometChatGroupsWithMessages
           android:id="@+id_group"
           android:layout_width="match_parent"
           android:layout_height="match_parent"
          _>
```



#### Usage in Fragment and Activity Class

```java
__for Fragment class
 @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
       return new CometChatGroupsWithMessages(getContext());
    }

__for Activity class
 @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
       setContentView(new CometChatGroupsWithMessages(this));
    }
```



### Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setGroup** | Group | used to automatically to navigate to the CometChatMessages component for the passed Group while the process for fetching conversations continues in the background | 
| **setGroupsConfiguration** | [GroupsConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/groups-configuration) | used to configure properties of `CometChatGroups` | 
| **setMessagesConfiguration** | [MessagesConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/messages-configuration) | Used to pass Message Configurations | 
| **setJoinGroupConfiguration** | [JoinProtectedGroupConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/join-protected-group-configuration) | used to configure properties of `CometChatJoinProtectedGroup` | 
| **setCreateGroupConfiguration** | CreateGroupConfiguration | used to configure properties of `CometChatCreateGroup` | 
