## Overview

CometChatCallDetails is a independent component used to set up a screen that shows the details of particular call for user or group object. It inherits all the properties and methods from the `CometChatListBase` class.

CometChatCallDetails sets up the following functionality internally:

- Details of Call for User or Group Object
- Revent components to perform additional operations on Call for User or Group object.

It includes all the business logic and options to customize the UI according to our default design system.

---

## Components

`CometChatCallDetails` is composed with the following widgets:

| Component | Description | 
| ---- | ---- | 
| [CometChatListBase](CometChatListBase) | a reusable container component having title, search box, customisable background and a List View | 
| [CometChatListItem](CometChatListItem) | a component that renders data obtained from a User object on a Tile having a title, subtitle, leading and trailing view | 


---

## Usage

CometChatCallDetails can be used inside another widget or can be launched to a new screen

```xml
<com.cometchat.chatuikit.calls.calldetails.CometChatCallDetails
        android:id="@+id_details"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setSubtitleView | Function3&lt;Context, User, Group, View&gt; | Used to set a custom subtitle for details | 
| setCustomProfileView | Function3&lt;Context, User, Group, View&gt; | Used to set a custom profile view in callDetails using this method will replace the default  CometChatListItem with the view provided. | 
| hideProfile | boolean | Used to hide profile view | 
| setHideError | boolean | Used to dialog appear when error is encountered. | 
| setUser | User | Used to set User against which the details need to be loaded | 
| setGroup | Group | Used to set Group against which the details need to be loaded | 
| setCall | Call | Used to set Call against which the details need to be loaded | 
| setData | Function3&lt;Context, User, Group, List&lt;CometChatDetailsTemplate&gt;&gt; | Used to set view or data that to be rendered below CometChatListItem. | 
| showCloseButton | boolean | Used to hide/unhide close button | 
| setCloseButtonIcon | @DrawableRes int | Used to set close button icon color | 
| setListItemStyle | ListItemStyle | Used to set ListItem Style | 
| setStatusIndicatorStyle | StatusIndicatorStyle | Used to set Status indicator style in ListItem | 
| setAvatarStyle | AvatarStyle | Used to set Avatar style in ListItem | 
| setOnError | OnError | Callback invoked upon encountering an error in the component | 


## DetailStyle

This property is used to customize the appearance of the `CometChatCallDetails` component

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setBackground | @ColorInt int | used to set background color | 
| setBackground | Drawable | used to set a gradient background | 
| setBorderWidth | int | used to set border | 
| setBorderColor | @ColorInt int | used to set border color | 
| setCornerRadius | double | used to set corner radius | 
| setTitleAppearance | @StyleRes int | used to set style of the title in the app bar | 
| setCloseIconTint | @ColorInt int | used to set the color of the back icon in the app bar | 
| setOnlineStatusColor | @ColorInt int | used to set the color of the status indicator shown if a user is online | 


```java
CometChatCallDetails details = view.findViewById(R.id.details);
DetailsStyle style = new DetailsStyle().setBackground(Color.parseColor("#ff606d"));
details.setStyle(style);
```



### data

A list of `CometChatDetailsTemplate` defines the structure for _[sections of options](https://app.developerhub.io/cometchat-documentation/v3/flutter-uikit-beta/details#cometchatdetailsoption)_ available in the CometChatDetails

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| setId | String | unique ID for the option | 
| setTitle | String | a text to display below the icon | 
| setTitleAppearance | @StyleRes int | used to set style of the text below the icon | 
| setOptions | Function2&lt;User, Group, List&lt;CometChatDetailsOption&gt;&gt; | options available under each section | 
| setSectionSeparatorColor | @ColorInt int | the color of the divider separating the sections of options | 
| hideSectionSeparator | boolean | if true doesn't show the divider separating the sections of options | 
| setItemSeparatorColor | @ColorInt int | the color of the divider separating the each option | 
| setHideItemSeparator | @ColorInt int | if true doesn't show the divider separating the each option | 


### Usage

```java
CometChatDetailsTemplate template=new CometChatDetailsTemplate().setId("TemplateID").setTitle("new  CometChatDetailsTemplate template=new CometChatDetailsTemplate().setId("TemplateID").setTitle("new template").hideSectionSeparator(true).setHideItemSeparator(false);

details.setData((context, user, group) -> {
            return Arrays.asList(template);
        });
```



## CometChatDetailsOption

`CometChatDetailsOption` is the class providing structure for options to be shown for users and group members

| Properties | Type | Description | 
| ---- | ---- | ---- | 
| id | String | unique ID for the option | 
| title | String | used to set title for the option | 
| startIcon | @DrawableRes int | used to set start icon for the option | 
| endIcon | @DrawableRes int | used to set end icon for the option | 
| titleColor | @ColorInt int | used to set title color | 
| titleFont | String | used to set title text font | 
| titleAppearance | @StyleRes int | used to set style of the title text | 
| startIconTint | @ColorInt int | set color of start icon | 
| endIconTint | @ColorInt int | set color of end icon | 
| onClick | OnDetailOptionClick | the action to perform on click of option | 
| view | Function3&lt;Context, User, Group, View&gt; | to set a custom view for particular option | 


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

