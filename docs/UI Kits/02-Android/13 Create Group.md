CometChatCreateGroup is an independent component used to set up a screen that shows the functionality to create a new group

`CometChatCreateGroup` sets up the following functionality internally:

- Create different types of group
- Customizable Tab Layout
- Customizable Input Box

`CometChatCreateGroup` component contains the following sub-components:

- [CometChatListBase](https://www.cometchat.com/docs/java-uikit-beta/list-base) : is a reusable container component having Title, Search, background and a list view

---

## Usage

Since `CometChatCreateGroup` can be launched by adding the following code snippet into the XML layout file.

#### Usage in XML

```xml
<com.cometchat.chatuikit.creategroup.CometChatCreateGroup
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:id="@+id_createGroup"_>
```



![](https://uploads.developerhub.io/prod/x9W8/va3z9kft505bpbnl726j5mso2kmdg3x4damlgdf933z5seafsq9xuub1hfxg7ris.png)

## Customization

There are various XML attributes that can be used to customize the appearance of the `CometChatCreateGroup`. The most useful ones include:

#### **Title**

| Attributes | Description | 
| ---- | ---- | 
| app:title | Used to change the title Text | 
| app:titleColor | Used to change color of title | 


#### **Back Icon**

| Attributes | Description | 
| ---- | ---- | 
| app:showBackButton | Used to set the visibility of back button | 
| app:backButtonIcon | Used to set user Back button icon | 
| app:backIconTint | Used to change the back icon tint color | 


#### **Create Group Icon**

| Attributes | Description | 
| ---- | ---- | 
| app:createGroupIcon | Used to set create group icon | 
| app:createGroupIconTint | Used to change the create group icon tint color | 


#### **Background**

| Attributes | Description | 
| ---- | ---- | 
| app:backgroundColor="@color/background" | Used to set background color of component | 


#### **Tabs**

| Attributes | Description | 
| ---- | ---- | 
| app:tabSelectedTextColor | Used to change selected tab text color | 
| app:tabTextColor | Used to change tab text color | 
| app:tabBackground | Used to change tab background drawable . | 
| app:tabBackgroundTint | Used to change the Tab background tint color | 
| app:tabBackgroundState | Used to set Tab background state drawable . | 
| app:tabIndicatorColor | Used to set Tab indicator color | 


```xml
<com.cometchatworkspace.components.groups.createGroup.CometChatCreateGroup
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:backgroundColor="#FF606D"                       
    android:id="@+id_createGroup"_>
```



---

## Methods

### **Background**

| Methods | Description | 
| ---- | ---- | 
| `setBackground(Drawable drawable)` | This method will set the background drawable for CometChatCreateGroup. | 
| `setBackground(@ColorInt int color)` | This method will set the background color for CometChatCreateGroup. | 
| `setBackground(int[] colorArray, GradientDrawable.Orientation orientation)` | This method will set the background color for CometChatCreateGroup. | 


```java
__ syntax for setBackground(Drawable drawable)
createGroup.setBackground(getResources().getDrawable(R.drawable.background));

__ syntax for setBackground(@ColorInt int color)
createGroup.setBackgroundColor(getResources().getColor(R.color.background));

__syntax for setBackground(int[] colorArray, GradientDrawable.Orientation orientation)
int colorArray[]={Color.parseColor("#7141e2"),Color.parseColor("#d46cb3")};
createGroup.setBackground(colorArray, GradientDrawable.Orientation.BL_TR);
```



### **StatusBar**

| Method | Description | 
| ---- | ---- | 
| setStatusColor(int color) | This Method will set the color of Status bar. | 


```java
createGroup.setStatusColor(getResources().getColor(R.color.purple));
```



### **Group Types**

| Methods | Description | 
| ---- | ---- | 
| hidePublicGroup() | Used to remove the option to create Public group. | 
| hidePrivateGroup() | Used to remove the option to create Private group. | 
| hidePasswordGroup() | Used to remove the option to create Password group. | 


```java
__ syntax for hidePublicGroup()
createGroup.hidePublicGroup();

__ syntax for hidePrivateGroup()
createGroup.hidePrivateGroup()

__syntax for hidePasswordGroup()
createGroup.hidePasswordGroup();
```



### **InputBox**

| Methods | Description | 
| ---- | ---- | 
| setEditTextCornerRadius(float EditTextBoxRadius) | Used to set corner radius to the Available EditText in the Component. | 
| setEditTextBackground(@ColorInt int EditTextBoxColor) | Used to set background color to the Available EditText in the Component. | 
| setEditTextPlaceHolderColor(@ColorInt int color) | Used to set placeholder color to the Available EditText in the Component. | 
| setEditTextTextColor(@ColorInt int color) | Used to set text color to the Available EditText in the Component. | 
| setEditTextTextFont(String fontName) | Used to set text font to the Available EditText in the Component. | 
| setEditTextTextAppearance(int appearance) | Used to set text appearance to the Available EditText in the Component. | 
| setEditTextBorderColor(@ColorInt int color) | Used to set border color to the Available EditText in the Component. | 
| setEditTextBorderWidth(int width) | Used to set border width to the Available EditText in the Component. | 


```java
__syntax to setEditTextCornerRadius
createGroup.setEditTextCornerRadius(12);

__syntax to setEditTextBackground
createGroup.setEditTextBackground(getResources().getColor(R.color.colorPrimary));
            
__syntax to setEditTextPlaceHolderColor
createGroup.setEditTextPlaceHolderColor(getResources().getColor(R.color.colorPrimary));
            
__syntax to setEditTextTextColor
createGroup.setEditTextTextColor(getResources().getColor(R.color.colorPrimary));

__syntax to setEditTextTextFont
createGroup.setEditTextTextFont("Roboto-Regular.ttf");
          
__syntax to setEditTextTextAppearance
createGroup.setEditTextTextAppearance(R.style.TextAppearance_AppCompat_Medium);

__syntax to setEditTextBorderColor
createGroup.setEditTextBorderColor(getResources().getColor(R.color.accent50));
            
__syntax to setEditTextBorderWidth
createGroup.setEditTextBorderWidth(5);
```



### **Name & Password inputbox**

The methods mentioned below are used to modify Name Inputbox and Password Inputbox separately. 

| Methods | Description | 
| ---- | ---- | 
| setPasswordInputBoxPlaceHolderText(String text) | Used to set placeholder text to the Password EditText present in the Component. | 
| setNameInputBoxPlaceHolderText(String text) | Used to set placeholder text to the Name EditText present in the Component. | 
| setPasswordInputBoxStartIconTint(@ColorInt int color) | Used to set start icon tint color to the Password EditText present in the Component. | 
| setNameInputBoxStartIconTint(@ColorInt int color) | Used to set start icon tint color to the Name EditText present in the Component. | 
| setPasswordInputBoxStartIcon(int res) | Used to set start icon to the Password EditText present in the Component. | 
| setNameInputBoxStartIcon(int res) | Used to set start icon to the Name EditText present in the Component. | 


```java
__syntax to setPasswordInputBoxPlaceHolderText
createGroup.setPasswordInputBoxPlaceHolderText("Password");
            
__syntax to setNameInputBoxPlaceHolderText
createGroup.setNameInputBoxPlaceHolderText("Name");
           
__syntax to setPasswordInputBoxStartIconTint
createGroup.setPasswordInputBoxStartIconTint(getResources().getColor(R.color.accent));
           
__syntax to setNameInputBoxStartIconTint
createGroup.setNameInputBoxStartIconTint(getResources().getColor(R.color.accent));
           
__syntax to setPasswordInputBoxStartIcon
createGroup.setPasswordInputBoxStartIcon(getResources().getDrawable(R.drawable.lock));
           
__syntax to setNameInputBoxStartIcon
createGroup.setNameInputBoxStartIcon(getResources().getDrawable(R.drawable.person));
```



### **Title**

| Methods | Description | 
| ---- | ---- | 
| setTitle(String title) | This method will set the title | 
| setTitleColor(@ColorInt int color) | This method will set the title color | 
| setTitleFont(String font) | This method will set the title font | 
| setTitleAppearance(int appearanceStyle) | This method will set the appearance of title | 


```java
__syntax to setTitleFont
createGroup.setTitleFont("Roboto-Regular.ttf");
          
__syntax to setTitleAppearance
createGroup.setTitleAppearance(R.style.TextAppearance_AppCompat_Medium);

__syntax to setTitleColor
createGroup.setTitleColor(getResources().getColor(R.color.accent50));
            
__syntax to setTitle
createGroup.setTitle("New Group");
```



### **Create Group**

| Method | Description | 
| ---- | ---- | 
| setCreateGroupIcon(Drawable createGroupIcon) | Used to Change Create group icon. | 


```java
createGroup.setCreateGroupIcon(getResources().getDrawable(R.drawable.create_group))
```



### Types of Groups

### **Public Groups**

This Types of groups can be joined by any one. whenever LoggedIn User perform click action they get joined to that particular group

![](https://uploads.developerhub.io/prod/x9W8/1v8pft656bouk6qrnvqjar4zn8v3zphdsnfa7v3u6z21ry3o88xmto2l05ew2an6.png)

### **Password Groups**

This Types of groups can not be joined by any one. To join these groups LoggedIn user will require a correct password.

![](https://uploads.developerhub.io/prod/x9W8/0nxwtlb6qzv4vasli63zv1ce53bblwjdpsqzh81we7zj5qb4vhs3s6hokmqs4od7.png)

### **Private Groups**

This groups are only visible to the LoggedIn user if he/she is a member of that group. They don't need to join Group therefore they can directly open [CometChatMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/messages) on a click of any private group shown in a [CometChatGroups](https://www.cometchat.com/docs/v3/android-v4-uikit/groups)