`CometChatStatusIndicator` is a customized component which indicates whether user is online or offline. You can customize the `borderColor`, `borderSize`, and `backgroundColor` of this component.

![](https://uploads.developerhub.io/prod/x9W8/ltyjb5ctoay86mcws67c02sfyfnsf6ffp68u0oznn0vp6m6f28tlfvdmsmhjxjhe.png)

## How to integrate CometChatStatusIndicator ?

Since `CometChatStatusIndicator` is a custom view, it can be added directly in the layout file or you can use it in Java. `CometChatStatusIndicator` includes various attributes and methods to customize its UI.

#### Usage in XML

```xml
<com.cometchat.chatuikit.shared.views.CometChatStatusIndicator.CometChatStatusIndicator
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:id="@+id_status"
        _>
```



## Methods

### **Customization**

This Methods are use to do modify the appearance of CometChatStatusIndicator

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setCornerRadius** | int | Used to set the cornerRadius | 
| **setBorderColor** | @ColorInt int | Used to set the borderColor | 
| **setBackgroundColor** | @ColorInt int | Used to set the backgroundColor | 
| **setBackgroundImage** | @DrawableRes int | Used to set the background image | 
| **setBorderWidth** | int | Used to set the borderWidth | 


```java
__syntax for cornerRadius(int radius)
status_indicator.setCornerRadius(100);

__syntax for borderColor(@ColorInt int color)
status_indicator.setBorderColor(getResources().getColor(R.color.black));

__syntax for setCardBackgroundColor(@ColorInt int color)
status_indicator.setCardBackgroundColor(Color.parseColor("#FF606D"));

__syntax for borderWidth(int borderWidth)
status_indicator.setBorderWidth(2);
```



![](https://uploads.developerhub.io/prod/x9W8/ml79uprjjck1ru7z271vjwoy8bqv4a93zuv4zs77q59tdzmti04zk7vu86uq4wuf.png)