## Overview

`CometChatActionSheet` is a component which present list of options in a list mode as well as grid mode as per the user's choice. By default, CometChatActionSheet is an integral part of CometChatMessageComposer to deliver multiple types of media as well as custom messages.

![](https://uploads.developerhub.io/prod/x9W8/b3p3eeft6cnnkubehgrvbhtx8hkmwzobx2e26575beuzja492hoo2xkw8cgu00ac.png)

---

## Data Model

`ActionItem` class is a Data Model used to set Data in every Item of Action Sheet.

| Parameters | Description | 
| ---- | ---- | 
| id | Used to set id so that every item in a list can be uniquely identify. | 
| text | Used to set name of the Item in a list. | 
| startIcon | Used to set start icon in a list item. | 


```java
__how to create Actionitem object to render in a list
ActionItem item = new ActionItem("id", "text",R.drawable.icon);
```



---

## How to integrate CometChatActionSheet ?

`CometChatActionSheet` can be launched in a UI by adding below lines of code it into the java file.

```java
__ syntax to create instance of CometChatActionSheet
CometChatActionSheet cometChatActionSheet = new CometChatActionSheet();
__syntax to create list of Action item need to be added in a Action Sheet
List<ActionItem> itemList = new ArrayList<>();
itemList.add(new ActionItem("id1","text1",R.drawable.icon));
itemList.add(new ActionItem("id2","text2",R.drawable.icon2));
__user can add as much as item they want in a Acionsheet

cometChatActionSheet.setList(itemList);
cometChatActionSheet.setLayoutMode(ActionSheet.LayoutMode.listMode); __ it can be also set to grid mode
```



---

## Methods

### **Set List**

This method is used to render the list of action items to be displayed in action sheet.

| Method | Description | 
| ---- | ---- | 
| setList(List&lt;ActionItem&gt; list) | Sets the list of action items to be displayed in action sheet. | 


```java
__syntax to create list of Action item need to be added in a Action Sheet
List<ActionItem> itemList = new ArrayList<>();
itemList.add(new ActionItem("id1","text1",R.drawable.icon));
itemList.add(new ActionItem("id2","text2",R.drawable.icon2));
__user can add as much as item they want in a Acionsheet

__syntax for setList(itemList)
cometChatActionSheet.setList(itemList);
```



### **Layout Mode**

This method is used to set the default layout for the action sheet. It takes the LayoutMode which has two values as mention below.

1. listMode
2. gridMode

| Method | Description | 
| ---- | ---- | 
| setLayoutMode(@ActionSheet.LayoutMode String mode) | Sets the default layout for the action sheet. It takes the LayoutMode which has two values.\n\n\n\n`.listMode, .gridMode` | 
| setLayoutModeIcon(Drawable icon) | Sets the layout mode icon. | 
| setLayoutModeIconTint(@ColorInt int color) | Sets the layout mode icon color. | 
| hideLayoutMode(boolean isHidden) | Used to hide/unhide layout mode icon. | 


```java
__syntax to set listMode
cometChatActionSheet.setLayoutMode(ActionSheet.LayoutMode.listMode); 
__syntax to set gridMode
cometChatActionSheet.setLayoutMode(ActionSheet.LayoutMode.gridMode);

__syntax for set layout mode icon
cometChatActionSheet.setLayoutModeIcon(getResources().getDrawable(R.drawable.icon));

__syntax for  setLayoutModeIconTint
cometChatActionSheet.setLayoutModeIconTint(getResources().getColor(R.color.accent50));

__syntax for hideLayoutMode
cometChatActionSheet.hideLayoutMode(false);
```



![](https://uploads.developerhub.io/prod/x9W8/6htpi8eb49tytr6dxfbtm8654wv2r9vdiax1ex8vr6b5ki6d2mgswaym4xfawhf8.png)

### **Title**

These attributes are used to modify the Title in `CometChatActionSheet` .

| Methods | Description | 
| ---- | ---- | 
| setTitle(String title) | Sets the title in Action Sheet | 
| setTitleColor(@ColorInt int color) | Sets the title color in Action Sheet | 
| setTitleFont(String font) | Sets the title font in Action Sheet | 


```java
____syntax to setTitle
cometChatActionSheet.setTitle("Action Sheet"); 

__syntax to setTitleFont
cometChatActionSheet.setTitleFont("Roboto-Regular.ttf");

__syntax to setTitleColor
cometChatActionSheet.setTitleColor(getResources().getColor(R.color.accent50));
```



Background

You will be able to modify the background color using the below methods:

| Method | Description | 
| ---- | ---- | 
| setBackground(@ColorInt int color) | This method will set the background color of Action Sheet. | 


```java
__ syntax for setBackground(@ColorInt int color)
cometChatActionSheet.setBackground(getResources().getColor(R.color.background));
```



### **Reactions**

You will  be able to hide/unhide reactions from the action Sheet.

| Method | Description | 
| ---- | ---- | 
| showReactions(boolean isVisible) | You will  be able to hide/unhide reactions from the action Sheet. | 


## Events

To receive the events when the user clicks on any item or reaction on an action sheet.

| Event | Description | 
| ---- | ---- | 
| onReactionClick(Reaction reaction) | Triggers when a reaction is Tapped | 
| onActionItemClick(ActionItem actionItem) | Triggers when any item is Tapped from a list of Action sheet | 


```java
cometChatActionSheet.setEventListener(new CometChatActionSheetListener() {
    @Override
    public void onReactionClick(Reaction reaction) {
        super.onReactionClick(reaction);
      
    }

    @Override
    public void onActionItemClick(ActionItem actionItem) {

    }
});
```
