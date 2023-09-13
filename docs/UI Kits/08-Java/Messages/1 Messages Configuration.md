You can modify the `CometChatMessages` component's properties using the `CometChatMessagesConfiguration` object. To use a configuration, you simply need to pass it to the parent component.

The `CometChatMessagesConfiguration` supports the following properties:

| Configuration | Description | 
| ---- | ---- | 
| `setMessageFilter(List<CometChatMessageTemplate> listOfMessageTemplate)` | Filter messages shown in CometChatMessages | 
| `setUserChatEnabled(boolean isEnabled)` | Enable/disable composeBox for 1-1 conversations | 
| `setGroupChatEnabled(boolean isEnabled)` | Enable/disable composeBox for group conversations | 
| background(int[] colors, GradientDrawable.Orientation orientation) | Sets gradient background to the CometChatMessages. | 
| background(@ColorInt int color) | Sets background color to the CometChatMessages. | 


## Step 1: Create CometChatMessagesConfiguration Object.

```java
__syntax to remove messages having image in it. 
List<CometChatMessageTemplate> list= TemplateUtils.remove(SelectActivity.this,CometChatMessageTemplate.DefaultList.image);
CometChatMessagesConfigurations configurations=new CometChatMessagesConfigurations()
        .setMessageFilter(list);
```



## Step 2: Provide it to Configurations in the particular module

```java
setConfiguration(configurations);
```

