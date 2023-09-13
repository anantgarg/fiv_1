`CometChatDetails` is a component that displays all the available options available to to execute and access further information about the passed `AppEntity` which may be an instance of [User](https://www.cometchat.com/docs/v3/android-chat-sdk/users) or [Group](https://www.cometchat.com/docs/v3/android-chat-sdk/groups). By default options to view profile, block and unblock user is available for an `User` object and options to view members, members banned from the group , leave group is available for an `Group` object, additionally options to transfer ownership of a group and deleting it is available if the logged in user happens to be the owner of the passed `Group` object.

`CometChatDetails` sets up the following functionality internally:

- verifies and fetching list of options.

### How to integrate CometChatDetails ?

Since `CometChatDetails` is a custom view, It can be launched by adding the following code snippet into the XML layout file.

Usage

```xml
<com.cometchat.chatuikit.details.CometChatDetails
        android:id="@+id_details"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



```java
CometChatDetails details = findViewById(R.id.details);
        if (user != null) details.setUser(user);
        else if (group != null) details.setGroup(group);
```



## Method

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setUser** | User | used validate and fetch list of available options for users | 
| **setGroup** | Group | used validate and fetch list of available options for groups | 
| **setTitle** | String | used to set the title in the app bar | 
| **setStyle** | DetailsStyle | used to customize the appearance of the widget | 
| **showCloseButton** | boolean | used to toggle visibility for back button | 
| **setCloseButtonIcon** | @DrawableRes int | used to set back button located in the app bar | 
| **setData** | Function3&lt;Context, User, Group, List&lt;CometChatDetailsTemplate&gt;&gt; | used to override list of templates is passed which is used for displaying relevant options | 
| **setGroupMembersConfiguration** | [GroupMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/group-members-configuration) | used to customize `CometChatGroupMembers` being used internally | 
| **setAddMembersConfiguration** | [AddMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/add-members-configuration) | used to customize `CometChatAddMembers` being used internally | 
| **setTransferOwnershipConfiguration** | [TransferOwnershipConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/transfer-ownership-configuration) | used to customize `CometChatTransferOwnerip` being used internally | 
| **setBannedMembersConfiguration** | [BannedMembersConfiguration](https://www.cometchat.com/docs/v3/android-v4-uikit/banned-members-configuration) | used to customize `CometChatBannedMembers` being used internally | 
| **disableUserPresence** | boolean | used to control visibility of status indicator shown if user is online | 
| **setMenu** | View | used to set the options available in the app bar | 
| **setListItemStyle** | ListItemStyle | used to set style to CometChatListItem which displays data obtained from an User or Group object | 
| **setStatusIndicatorStyle** | StatusIndicatorStyle | used to customise the status indicator shown if a user is online | 
| **setAvatarStyle** | AvatarStyle | used to customise the Avatar of the user and group shown in the leading view of the list item | 
| **setPrivateGroupIcon** | @DrawableRes int | used to set icon shown in place of status indicator if the details component is being rendered for a private group | 
| **setProtectedGroupIcon** | @DrawableRes int | used to set icon shown in place of status indicator if the details component is being rendered for a password protected group | 
| **setSubtitleView** | Function3&lt;Context, User, Group, View&gt; | used to set a custom subtitle for the list item | 
| **setCustomProfileView** | Function3&lt;Context, User, Group, View&gt; | provides a customized view profile for users | 
| **hideProfile** | boolean | hides view profile option for users | 
| **addOnBackPressListener** | OnBackPress | used to set a call back triggered on tapping the back button in the app bar | 
| **setOnError** | OnError | used to set a callback triggered in case any error happens when fetching detail option or performing any action | 


### detailsStyle

This methods is used to customize the appearance of the `CometChatDetails` component

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setBackground | @ColorInt\n\nint | used to set background color | 
| setBackground | Drawable | used to set a gradient background | 
| setBorderWidth | int | used to set border | 
| setBorderColor | @ColorInt\n\nint | used to set border color | 
| setCornerRadius | double | used to set corner radius | 
| setTitleAppearance | @StyleRes\n\nint | used to set style of the title in the app bar | 
| setCloseIconTint | @ColorInt\n\nint | used to set the color of the back icon in the app bar | 
| setOnlineStatusColor | @ColorInt\n\nint | used to set the color of the status indicator shown if a user is online | 


```java
CometChatDetails details = view.findViewById(R.id.details);
DetailsStyle style = new DetailsStyle();
style.setBackground(Color.parseColor("#ff606d"));
details.setStyle(style);
```



### data

A list of `CometChatDetailsTemplate` defines the structure for sections of options available in the CometChatDetails

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setId | String | unique ID for the option | 
| setTitle | String | a text to display below the icon | 
| setTitleAppearance | @StyleRes\n\nint | used to set style of the text below the icon | 
| setOptions | Function2&lt;User, Group, List&lt;CometChatDetailsOption&gt;&gt; | options available under each section | 
| setSectionSeparatorColor | @ColorInt\n\nint | the color of the divider separating the sections of options | 
| hideSectionSeparator | boolean | if true doesn't show the divider separating the sections of options | 
| setItemSeparatorColor | @ColorInt\n\nint | the color of the divider separating the each option | 
| setHideItemSeparator | @ColorInt\n\nint | if true doesn't show the divider separating the each option | 


#### Usage

```java
CometChatDetailsTemplate template=new CometChatDetailsTemplate().setId("TemplateID").setTitle("new template").hideSectionSeparator(true).setHideItemSeparator(false);

details.setData((context, user, group) -> {
            return Arrays.asList(template);
        });
```



## CometChatDetailsOption

`CometChatDetailsOption` is the class providing structure for options to be shown for users and group members

| properties | Type | Description | 
| ---- | ---- | ---- | 
| id | String | unique ID for the option | 
| title | String | used to set title for the option | 
| startIcon | @DrawableRes int | used to set start icon for the option | 
| endIcon | @DrawableRes int | used to set end icon for the option | 
| titleColor | @ColorInt\n\nint | used to set title color | 
| titleFont | String | used to set title text font | 
| titleAppearance | @StyleRes int | used to set style of the title text | 
| startIconTint | @ColorInt\n\nint | set color of start icon | 
| endIconTint | @ColorInt\n\nint | set color of end icon | 
| onClick | OnDetailOptionClick | the action to perform on click of option | 
| view | Function3&lt;Context, User, Group, View&gt; | to set a custom view for particular option | 


### Usage

```java
__create custom option
CometChatDetailsOption  option= new CometChatDetailsOption(UIKitConstants.UserOption.VIEW_PROFILE,getString(com.cometchat.chatuikit.R.string.view_profile), 0, 0, Palette.getInstance(getContext()).getPrimary(), null, Typography.getInstance().getName(), 0, Palette.getInstance(getContext()).getAccent200(), null);


__create custom option with custom view
CometChatDetailsOption customViewOption = new CometChatDetailsOption(((context, user, group) -> {
            TextView textView = new TextView(context);
            textView.setText("custom view for detail option");
            return textView;
        }), new OnDetailOptionClick() {
            @Override
            public void onClick(User user, Group group, String templateId, CometChatDetailsOption option, Context context) {
							__perform on click operation
            }
        });

CometChatDetailsTemplate template=new CometChatDetailsTemplate()
                .setId("TemplateID")
                .setTitle("new template")
                .hideSectionSeparator(true)
                .setHideItemSeparator(false)
                .setOptions((var1, var2) -> {
                   return Arrays.asList(option,customViewOption);
                });

        details.setData((context, user, group) -> {
            return Arrays.asList(template);
        });
```

