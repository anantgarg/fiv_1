`CometChatJoinProtectedGroup` is an independent component used to set up a screen that shows the functionality to join a password protected group.

`CometChatJoinProtectedGroup` sets up the following functionality internally:

- User will be able to join single password protected group at a time.
- It includes all the business logic and options to customize the UI according to our default design system.

`CometChatJoinProtectedGroup` component contains the following sub-components:

- [CometChatListBase](https://www.cometchat.com/docs/java-uikit-beta/list-base) : is a reusable container component having Title, Search, background and a list view

---

## Usage

`CometChatJoinProtectedGroup` can be launched by adding the following code snippet into the XML layout file.

```xml
<com.cometchatworkspace.components.groups.CometChatJoinProtectedGroup
        android:id="@+id_joinGroup"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>
```



![](https://uploads.developerhub.io/prod/x9W8/7mzislqkeq8tv3ezvhbog0tdnm5gki1wsvopvtzsq7oeello31i1cajap3xx5pdk.png)

## Customization

CometChatJoinProtectedGroup provides a list of xml attributes available for customization

#### **Title**

| Attributes | Description | 
| ---- | ---- | 
| app:title | Used to change the text of title. | 
| app:titleColor | Used to change the color of title. | 


#### **Label**

| Attributes | Description | 
| ---- | ---- | 
| app:labelText | Used to change the lable text. | 
| app:labelColor | Used to change the lable color. | 
| app:showLabel | Used to control the visibility of lable. | 


#### **Back Icon**

| Attributes | Description | 
| ---- | ---- | 
| app:backIconTint | Used to change the back button color. | 
| app:showBackButton | Used to modify the visibility of back button. | 
| app:backButtonIcon | Used to change the back button. | 


#### **Join Group**

| Attributes | Description | 
| ---- | ---- | 
| app:joinGroupIconTint | Used to change the join group icon color. | 
| app:joinGroupIcon | Used to change the join group icon. | 


#### **EditText**

| Attributes | Description | 
| ---- | ---- | 
| app:editTextPlaceHolderText | Used to set the hint text in Password input box | 
| app:editBoxBackgroundColor | Used to change the Password input box background color | 
| app:editBoxBorderColor | Used to change the Password input box border color | 
| app:editBoxTextColor | Used to change the Password input box text color | 
| app:editTextPlaceHolderColor | Used to change the Password input box hint color | 
| app:editBoxCornerRadius | Used to change the Password Input box corner radius | 
| app:editBoxBorderWidth | Used to change the Password input box border width | 


```xml
<com.cometchat.chatuikit.joinprotectedgroup.CometChatJoinProtectedGroup
        android:id="@+id_joinGroup"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:title="Protected Group"
        app:titleColor="@color_accent"
        app:labelText="Enter password to access "
        app:labelColor="@color_black"
        app:editTextPlaceHolderText="group password"
        app:backIconTint="@color_primary"
        app:joinGroupIconTint="@color_primary"
        app:backgroundColor="#FF606D"
        _>
```



---

## Methods

### **Core Method**

This method is very important in order to use CometChatJoinProtectedGroup .

| Method | Description | 
| ---- | ---- | 
| setGroup(Group group) | Used set sdk's Group object in CometChatJoinProtectedGroup | 


```java
__syntax to setGroup
joinGroup.setGroup(group);
```



### **Title**

| Methods | Description | 
| ---- | ---- | 
| setTitle(String title) | This method will set the title. | 
| setTitleColor(@ColorInt int color) | This method will set the title color. | 
| setTitleFont(String font) | This method will set the title font. | 
| setTitleAppearance(int appearanceStyle) | This method will set the appearance of title. | 


```java
__syntax to setTitleFont
joinGroup.setTitleFont("Roboto-Regular.ttf");
          
__syntax to setTitleAppearance
joinGroup.setTitleAppearance(R.style.TextAppearance_AppCompat_Medium);

__syntax to setTitleColor
joinGroup.setTitleColor(Color.parseColor("#FF606D"));
            
__syntax to setTitle
joinGroup.setTitle("Join Group");
```



### **Label**

| Methods | Description | 
| ---- | ---- | 
| setLabelText(String labelText) | Used to set Label Text | 
| setLabelColor(int color) | Used to set Label color | 
| setLabelAppearance(int appearance) | Used to set Label Appearance | 
| setShowLabel(boolean showLabel) | Used to set visibility of the Lable | 


```java
__syntax to setTitleFont
joinGroup.setTitleFont("Roboto-Regular.ttf");
          
__syntax to setLabelAppearance
joinGroup.setLabelAppearance(R.style.TextAppearance_AppCompat_Medium);

__syntax to setLabelColor
joinGroup.setLabelColor(Color.parseColor("#FF606D"));
            
__syntax to setLabelText
joinGroup.setLabelText("Enter password to access");
```



### **StatusBar**

| Method | Description | 
| ---- | ---- | 
| setStatusColor(int color) | This Method will set the color of Status bar. | 


```java
joinGroup.setStatusColor(getResources().getColor(R.color.purple));
```



### **Back button**

| Methods | Description | 
| ---- | ---- | 
| setShowBackButton(boolean showBackButton) | Used to set Visibility of the Back button | 
| setBackButtonIcon(Drawable backButtonIcon) | Used to change the back icon of back button | 
| setBackIconTint(int backIconTint) | Used to change the back icon color | 


```java
__syntax to setShowBackButton
joinGroup.setShowBackButton(true);
          
__syntax to setBackButtonIcon
joinGroup.setBackButtonIcon(getResources().getDrawable(R.drawable.icon));

__syntax to setBackIconTint
joinGroup.setBackIconTint(getResources().getColor(R.color.black));
```



### **EditText**

| Method | Description | 
| ---- | ---- | 
| setEditTextCornerRadius(float EditTextBoxRadius) | Used To set corner radius in Password input field | 
| setEditTextBackground(@ColorInt int EditTextBoxColor) | Used to set Background in Password input field | 
| setEditTextPlaceHolderColor(@ColorInt int color) | Used to set Hint color in Password input field | 
| setEditTextPlaceHolderText(String placeHolderText) | Used to set Hint Text in Password input field | 
| setEditTextTextColor(@ColorInt int color) | Used to set Password input field text | 
| setEditTextTextFont(String fontName) | Used to set text font of Password input field | 
| setEditTextTextAppearance(int appearance) | Used to set text appearance in Password input field | 
| setEditTextBorderColor(@ColorInt int color) | Used to set Password input field border color | 
| setEditTextBorderWidth(int width) | Used to set Password input field border width | 
| setStartIconTint(@ColorInt int color) | Used to set start icon tint in Password input field | 
| setEditTextBoxStartIcon(int res) | Used to set start icon in Password input field | 


```java
__syntax to setShowBackButton
joinGroup.setShowBackButton(true);

__syntax to setEditTextCornerRadius
joinGroup.setEditTextCornerRadius(12);
  
__syntax to setEditTextBackground
joinGroup.setEditTextBackground(getResources().getColor(R.color.primary));

__syntax to setEditTextPlaceHolderText
joinGroup.setEditTextPlaceHolderText("Group Password");
  
__syntax to setEditTextTextColor
joinGroup.setEditTextTextColor(getResources().getColor(R.color.primary));

__syntax to setEditTextTextFont
joinGroup.setEditTextTextFont("Roboto-Regular.ttf");

__syntax to setEditTextTextAppearance
joinGroup.setEditTextTextAppearance(R.style.Heading);

__syntax to setEditTextBorderColor
joinGroup.setEditTextBorderColor(getResources().getColor(R.color.primary));

__syntax to setEditTextBorderWidth
joinGroup.setEditTextBorderWidth(2);

__syntax to setStartIconTint
joinGroup.setStartIconTint(getResources().getColor(R.color.primary));

__syntax to setEditTextBoxStartIcon
joinGroup.setEditTextBoxStartIcon(getResources().getDrawable(R.drawable.icon));
```



> `CometChatUsers` is the child of [CometChatListBase](https://www.cometchat.com/docs/java-uikit-beta/list-base) , Therefore it inherits all the methods that `CometChatListBase` contain.

---