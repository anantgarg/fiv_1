`CometChatBadge` is the custom component which is used to display the unread message count. It can be used in places like CometChatListItem, etc.

![](https://uploads.developerhub.io/prod/x9W8/wlt51ffbhd9jzdg7z6lnte79sev416ugyokd5w9o8uszp42sdob3zxfmx2ar8eg6.png)

---

## How to integrate CometChatBadgeCount ?

Since `CometChatBadge` is a custom view, it can be added directly in the layout file or you can use it in Java. `CometChatBadge` includes various attributes and methods to customize its UI.

#### Usage in XML

```xml
<com.cometchat.chatuikit.shared.views.CometChatBadge.CometChatBadge
        android:id="@+id_badge"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content" _>
```



## XML Attributes

| Parameters | Description | 
| ---- | ---- | 
| `app:count_background_color` | Used to set the backgroundColor | 
| `app:strokeWidth` | Used to set the borderWidth | 
| `app:count` | Used to set value of count. | 
| `app:count_color` | Used to set color of count value. | 
| `app:count_size` | Used to set text size of count value | 


```xml
<com.cometchat.chatuikit.shared.views.CometChatBadge.CometChatBadge
                android:layout_gravity="center"
                android:layout_width="wrap_content"
                app:count="1"
                app:count_background_color="@color_colorPrimaryDark"
                app:count_color="@color_light_grey"
                android:id="@+id_badge"
                android:layout_height="wrap_content"_>
```



## Methods

### **Customization**

This Methods are use to do modify the appearance of CometChatBadge

| Methods | Description | 
| ---- | ---- | 
| **cornerRadius(float radius)** | Used to set the cornerRadius | 
| **borderColor(@ColorInt int color)** | Used to set the borderColor | 
| **setBackground(@ColorInt int color)** | Used to set the backgroundColor | 
| **borderWidth(int width)** | Used to set the borderWidth | 
| **setCount(int counValue)** | Used to set value of count. | 
| **setTextColor(@ColorInt int color)** | Used to set color of count value(TextView) | 
| **setTextSize(float size)** | Used to set text size of count value | 


```java
CometChatBadge badge = findViewById(R.id.badge);
__syntax for cornerRadius(float radius)
badge.cornerRadius(18);

__syntax for borderColor(@ColorInt int color)
badge.borderColor(getResources().getDrawable(R.drawable.stroke_color));

__syntax for setBackground(@ColorInt int color)
badge.setBackground(getResources().getDrawable(R.drawable.background));

__syntax for borderWidth(int width)
badge.borderWidth(1);

__syntax for setCount(int counValue)
badge.setCount(12);

__syntax for setTextColor(@ColorInt int color)
badge.setTextColor(getResources().getDrawable(R.drawable.count_color));

__syntax for setTextSize(float size)
badge.setTextSize(10);
```

