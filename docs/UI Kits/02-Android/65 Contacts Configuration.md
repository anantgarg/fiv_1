You can modify the [CometChatContacts](https://www.cometchat.com/docs/v3/android-v4-uikit/contacts) component's properties using the `ContactsConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `ContactsConfiguration` supports the following properties:

| Methods | Parameter | Description | 
| ---- | ---- | ---- | 
| **setTitle(String title)** | String | Sets the title that will be displayed at the top of the `CometChatContacts` view. This method allows you to customize the title to provide relevant information or context to the users. | 
| **setCloseIcon (@DrawableRes int closeButtonIcon)** | @DrawableRes int | Sets the icon that will be displayed as the close button in the `CometChatContacts` view. | 
| **setSubmitIcon(@DrawableRes int submitIcon)** | @DrawableRes int | Sets the icon that will be displayed as the submit icon in the `CometChatContacts` view. | 
| **setOnSubmitIconClick(OnSelection onSelection)** | OnSelection | Sets the listener that will be triggered when the submit icon is clicked in the `CometChatContacts` view. The listener can be used to handle Contacts selection events, allowing users to perform actions based on the selected users and groups. | 
| **setStyle(ContactsStyle style)** | ContactsStyle | Sets various style configurations for the `CometChatContacts` view, including title appearance, font, color, background, border, tab colors, and more. | 
| **setUsersTabTitle(String title)** | String | Sets the title for the Users tab in the `CometChatContacts` view. This method allows you to customize the title displayed for the Users tab. | 
| **setGroupsTabTitle(String title)** | String | Sets the title for the Groups tab in the `CometChatContacts` view. This method allows you to customize the title displayed for the Groups tab. | 
| **setUsersConfiguration(UsersConfiguration configuration)** | UsersConfiguration | Sets the configuration for the Users tab in the `CometChatContacts` view. This method allows you to customize various aspects of the Users tab, such as search functionality, appearance and more. By passing a valid `UsersConfiguration` object, you can control how the Users tab behaves and appears to the users. | 
| **setGroupsConfiguration(GroupsConfiguration configuration)** | GroupsConfiguration | Sets the configuration for the Groups tab in the `CometChatContacts` view. This method allows you to customize various aspects of the Groups tab, such as search functionality, appearance and more. By passing a valid `GroupsConfiguration` object, you can control how the Groups tab behaves and appears to the users. | 


## How to create a ContactsConfiguration object and use it ?

please refer the below code snippet to create the object of ContactsConfiguration and configure it

```java
ContactsConfiguration contactsConfiguration = new ContactsConfiguration();
contactsConfiguration.setUsersTabTitle("Users");
```



## Usage

ContactsConfiguration can be used in a widget where CometChatConversations is present as a child component. We just pass that `ContactsConfiguration` object to the CometChatConversationsWithMessages widget.

```java
CometChatConversationWithMessages.setStartConversationConfiguration(contactsConfiguration);
```

