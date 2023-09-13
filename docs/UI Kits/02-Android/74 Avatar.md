`CometChatAvatar` component displays an image or user's avatar with fallback to the first two letters of the username or group's icon with fallback to the first two letter of the group name.

![](https://uploads.developerhub.io/prod/x9W8/iaut9ris3qsp06esxrfgn13x9y6uzpulcrgiocg97f47keqml8k1zc3tbi2osmdq.png)

---

## How to integrate CometChatAvatar ?

Since `CometChatAvatar` is a custom view, it can be added directly in the layout file or you can use it in Java. `CometChatAvatar` includes various attributes and methods to customize its UI.

#### Usage in XML

```xml
<com.cometchat.chatuikit.shared.views.CometChatAvatar.CometChatAvatar
        android:id="@+id_item_avatar"
        android:layout_width="40dp"
        android:layout_height="40dp"
       _>
```



## XML Attributes

| Parameters | Description | 
| ---- | ---- | 
| `app:corner_radius="18dp"` | Used to set the cornerRadius | 
| `app:border_color="@color/red"` | Used to set the borderColor | 
| `app:background_color="@color/blue"` | Used to set the backgroundColor | 
| `app:border_width="5dp"` | Used to set the borderWidth | 


```xml
<com.cometchat.chatuikit.shared.views.CometChatAvatar.CometChatAvatar
                android:id="@+id_avataricon"
                android:layout_width="100dp"
                android:layout_height="100dp"
                android:layout_gravity="center"                                                                     			tools:src="@tools:sample_avatars"_>
```



## Methods

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setImage** | String | Image will be obtained from path from assets. if name and image both are passed image will be visible | 
| `**setName**` | String | Used to can specify name to be shown in avatar (initials only), if image is not available | 
| **setStyle** | AvatarStyle | Used to customize appearance of the Avatar | 


## AvatarStyle

| Methods | Type | Description | 
| ---- | ---- | ---- | 
| **setHeight** | double | used to set height | 
| **setWidth** | double | used to set width | 
| **setBorderWidth** | BoxBorder | used to set border of the inner circle | 
| **setBackground** | Color | used to set background color | 
| **setBackground** | Gradient | used to set a gradient background | 
| **setCornerRadius** | double | used to modify the corner radius of inner circle | 
| **setOuterCornerRadius** | double | used to modify the corner radius of outer circle | 
| **setOuterBorderWidth** | BoxBorder | used to modify the border of outer circle | 
| **setInnerViewWidth** | double | used to modify the border width of outer circle | 
| **setOuterBackgroundColor** | Color | used to modify the background color of outer circle | 
| **setOuterViewSpacing** | double | used to modify spacing between the image and the outer border | 
| **setTextAppearance** | TextStyle | used to modify the text style for name if image is not available | 


```java
AvatarStyle avatarStyle =  new AvatarStyle();
                avatarStyle.setInnerViewBorderColor(getResources().getColor(android.R.color.holo_red_dark))
 avatarStyle.setInnerViewRadius(100)
 avatarStyle.setOuterBorderWidth(10)
 avatarStyle.setInnerViewWidth(10)
 avatarStyle.setOuterBorderColor(getResources().getColor(android.R.color.black));

 CometChatAvatar avatar=view.findViewById(R.id.item_avatar);
 avatar.setStyle(avatarStyle);
```



![](https://uploads.developerhub.io/prod/x9W8/wux7v74eleaj8lc50o3zp5ov94rz5qf0j599wlfih0e0kevz0dbs3nohnhpl17l0.png)