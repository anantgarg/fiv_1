`CometChatConversationsWithMessages` can be launched by adding the following code snippet into XML layout file.

```xml
<com.cometchat.chatuikit.conversationswithmessages.CometChatConversationsWithMessages
        android:id="@+id_conversationWithMessages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



paste this image into the drawable folder as a name of rocket_img.

![](https://uploads.developerhub.io/prod/x9W8/23mzbbs23kqb757ryx6m9qdhahgtwptr35elrbd8xjapm9rm1o3fn73tc6o8mdf9.png)

follow the below code to configure the Messages Component

```java
CometChatConversationsWithMessages conversationWithMessages = view.findViewById(R.id.conversationWithMessages);

__get Default templates 
List<CometChatMessageTemplate> templates = CometChatUIKit.getDataSource().getMessageTemplates();

__create new template
CometChatMessageTemplate nudgeTemplate = new CometChatMessageTemplate().setType("nudge").setCategory(UIKitConstants.MessageCategory.CUSTOM).setContentView((context, baseMessage, messageBubbleAlignment) -> {
            CometChatStickerBubble stickerBubble = new CometChatStickerBubble(context);
            stickerBubble.setDrawable(getResources().getDrawable(R.drawable.rocket_img));
            return stickerBubble;
        });

__add newly created template into the default list of template
templates.add(nudgeTemplate);

MessageListConfiguration messageListConfiguration = new MessageListConfiguration().setTemplates(templates);

MessageComposerConfiguration composerConfiguration = new MessageComposerConfiguration().setAuxiliaryButtonView((context, user, group, idMap) -> {
            ImageView imageView = new ImageView(context);
            ViewGroup.LayoutParams params = new ViewGroup.LayoutParams(100, 100);
            imageView.setImageResource(R.drawable.rocket_img);
            imageView.setLayoutParams(params);
            imageView.setOnClickListener(view1 -> {
                JSONObject jsonObject = new JSONObject();
                try {
                    jsonObject.put("type", "nudge");
                } catch (Exception e) {
                    e.printStackTrace();
                }
                CustomMessage customMessage = new CustomMessage(user != null ? user.getUid() : 		                                     group.getGuid(), user != null ? UIKitConstants.ReceiverType.USER :                                       UIKitConstants.ReceiverType.GROUP, "nudge", jsonObject);
                customMessage.setSender(CometChatUIKit.getLoggedInUser());
                customMessage.setSentAt(System.currentTimeMillis() _ 1000);
                customMessage.setMuid(System.currentTimeMillis() + "");
                customMessage.setReceiver(user != null ? user : group);
              if (idMap.containsKey(UIKitConstants.MapId.PARENT_MESSAGE_ID)) {
 customMessage.setParentMessageId(Integer.valueOf(idMap.get(UIKitConstants.MapId.PARENT_MESSAGE_ID)));
                        }
                CometChatUIKit.sendCustomMessage(customMessage);
            });
            return imageView;
        });

conversationWithMessages.setMessagesConfiguration(new MessagesConfiguration().setMessageListConfiguration(messageListConfiguration).setMessageComposerConfiguration(composerConfiguration));
```



End Result

![](https://uploads.developerhub.io/prod/x9W8/t4tbjeqegol0gi741ezuu89e38508780jiif5taqpheh85yx4eyx060febgilrz7.png)