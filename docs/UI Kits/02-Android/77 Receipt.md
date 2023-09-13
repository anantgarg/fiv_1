The CometChatReceipt component renders the  receipts such as sending, sent, delivered, read and error state indicator of a message.

![](https://uploads.developerhub.io/prod/x9W8/a1w8ok8jbsn50ui54tdfv1qqk5yregcweimaoo5kdk2eymhorifbpx6ksagig4g7.png)

## How to integrate CometChatReceipt ?

Since `CometChatReceipt` is a custom view, it can be added directly in the layout file or you can use it in Java. `CometChatReceipt` includes various attributes and methods to customize its UI.

#### Usage in XML

```xml
<com.cometchat.chatuikit.shared.views.CometChatReceipt.CometChatReceipt
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id_receipt"
        _>
```



## XML Attributes

To style or customize the `CometChatMessageReceipt`, you can use the available parameters or methods.

| Attributes | Description | 
| ---- | ---- | 
| app:messageProgressIcon | It is use to pass user defined image in to the MessageReceipt, to change the icon While sending the message. | 
| app:messageSentIcon | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is sent. | 
| app:messageDeliveredIcon | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is delivered. | 
| app:messageReadIcon | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is read. | 
| app:messageErrorIcon | It is use to pass user defined image in to the MessageReceipt, to change the icon While error occurs. | 


```xml
<com.cometchatworkspace.components.shared.secondaryComponents.CometChatMessageReceipt
                android:id="@+id_receipt"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                app:messageProgressIcon="@drawable_ic_message_progress"
                app:messageSentIcon="@drawable_ic_message_sent"
                app:messageDeliveredIcon="@drawable_ic_message_delivered"
                app:messageReadIcon="@drawable_ic_message_read"
                app:messageErrorIcon="@drawable_ic_message_error"        
                  _>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setReceipt** | Receipt | This method is used to set receipt | 
| **setWaitIcon** | Drawable | It is use to pass user defined image in to the MessageReceipt, to change the icon While sending the message. | 
| **setSentIcon** | Drawable | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is sent. | 
| **setDeliveredIcon** | Drawable | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is delivered. | 
| **setReadIcon** | Drawable | It is use to pass user defined image in to the MessageReceipt, to change the icon When Message is read. | 
| **setErrorIcon** | Drawable | It is use to pass user defined image in to the MessageReceipt, to change the icon While error occurs. | 


```java
CometChatReceipt receipt = findViewById(R.id.receipt);
__syntax for setReceipt(Receipt)
receipt.setReceipt(Receipt.SENT);
__syntax for setDeliveredIcon
receipt.setDeliveredIcon(getResources().getDrawable(R.drawable.ic_message_delivered));
__syntax for setReadIcon  
receipt.setReadIcon(getResources().getDrawable(R.drawable.ic_message_read));
__syntax for setSentIcon  
receipt.setSentIcon(getResources().getDrawable(R.drawable.ic_message_sent));
__syntax for setWaitIcon  
receipt.setWaitIcon(getResources().getDrawable(R.drawable.cc_progress_drawable));
__syntax for setErrorIcon  
receipt.setErrorIcon(getResources().getDrawable(R.drawable.cc_error));
```

