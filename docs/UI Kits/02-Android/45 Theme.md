CometChatTheme is a style applied to an every component. Thus, when a style is applied as a theme, every View in the Activity or every component in UiKit will apply each Theme property that it supports.

## Integration

### **Light Theme**

The `Light` theme is applied by default as it is shown in the image below, To switch it into the dark theme refer to the below code.

```java
__ get Instance of the Palette class
Palette palette = Palette.getInstance(this);
__set Mode
palette.mode(CometChatTheme.MODE.DARK);
```



![](https://uploads.developerhub.io/prod/x9W8/zba5bs9th44m48o2dem0wiyh9avbwgjl25a0vqmao8703r7j4d6wa1w9wodtipdd.png)

## Palette

Palette is a singleton class which contain all the color variable with the default value in it. as methods stated below with the default value

| Methods | Default Light mode value | Default Dark mode value | 
| ---- | ---- | ---- | 
| getBackground() | #FFFFFF | #99141414 | 
| getGradientBackground() | null | null | 
| getPrimary() | #3399FF | #3399FF | 
| getSecondary() | #ebf8f8f8 | #ebf8f8f8 | 
| getError() | #FF3B30 | #FF3B30 | 
| getAccent() | #141414 | #FFFFFF | 
| getAccent50() | #0a141414 | #0affffff | 
| getAccent100() | #14141414 | #14ffffff | 
| getAccent200() | #26141414 | #24ffffff | 
| getAccent300() | #3d141414 | #3bffffff | 
| getAccent400() | #54141414 | #57ffffff | 
| getAccent500() | #75141414 | #75ffffff | 
| getAccent600() | #94141414 | #94ffffff | 
| getAccent700() | #45141414 | #b5ffffff | 
| getAccent800() | #d1141414 | #d6ffffff | 
| getAccent900() | #FFFFFF | #141414 | 


## Typography

Typography is a singleton class which contain all the default Text Style's value in it. you can refer to the methods stated below with the default value.

| Methods | Default value | 
| ---- | ---- | 
| getHeading() | &lt;style name="Heading"&gt;\n\n    &lt;item name="android:fontWeight"&gt;500&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;20sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getName() | &lt;style name="Name"&gt;\n\n    &lt;item name="android:fontWeight"&gt;500&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;17sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getTitle1() | &lt;style name="Title1"&gt;\n\n    &lt;item name="android:fontWeight"&gt;600&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;15sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getTitle2() | &lt;style name="Title2"&gt;\n\n    &lt;item name="android:fontWeight"&gt;400&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;22sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getSubtitle1() | &lt;style name="Subtitle1"&gt;\n\n    &lt;item name="android:fontWeight"&gt;400&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;15sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getSubtitle2() | &lt;style name="Subtitle2"&gt;\n\n    &lt;item name="android:fontWeight"&gt;400&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;13sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getText1() | &lt;style name="Text1"&gt;\n\n    &lt;item name="android:fontWeight"&gt;400&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;17sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getText2() | &lt;style name="Text2"&gt;\n\n    &lt;item name="android:fontWeight"&gt;500&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;13sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getCaption1() | &lt;style name="Caption1"&gt;\n\n    &lt;item name="android:fontWeight"&gt;500&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;12sp&lt;/item&gt;\n\n&lt;/style&gt; | 
| getCaption2() | &lt;style name="Caption2"&gt;\n\n    &lt;item name="android:fontWeight"&gt;500&lt;/item&gt;\n\n    &lt;item name="android:fontFamily"&gt;roboto&lt;/item&gt;\n\n    &lt;item name="android:textSize"&gt;11sp&lt;/item&gt;\n\n&lt;/style&gt; | 


## Customization

There is a Total of 2 Classes, Palette and Typography that is responsible for customizing CometChatTheme.

### **Palette**

Palette contain methods which is use to change default color from the Theme as per user need.

| Methods | Description | 
| ---- | ---- | 
| background(@ColorInt int color) | Use to change the default background color | 
| gradientBackground(Drawable drawable) | Use to set gradient background by accepting gradient resource file | 
| gradientBackground(int[] colorArray, GradientDrawable.Orientation orientation) | Use to set gradient background by accepting array of color and orientation of the gradient | 
| primary(@ColorInt int color) | Use to change the default primary color | 
| secondary(@ColorInt int color) | Use to change the default secondary color | 
| error(@ColorInt int color) | Use to change the default error color | 
| accent(@ColorInt int color) | Use to change the default accent color | 
| accent50(@ColorInt int color) | Use to change the default accent50 color | 
| accent100(@ColorInt int color) | Use to change the default accent100 color | 
| accent200(@ColorInt int color) | Use to change the default accent200 color | 
| accent300(@ColorInt int color) | Use to change the default accent300 color | 
| accent400(@ColorInt int color) | Use to change the default accent400 color | 
| accent500(@ColorInt int color) | Use to change the default accent500 color | 
| accent600(@ColorInt int color) | Use to change the default accent600 color | 
| accent700(@ColorInt int color) | Use to change the default accent700 color | 
| accent800(@ColorInt int color) | Use to change the default accent800 color | 
| accent900(@ColorInt int color) | Use to change the default accent900 color | 


To change Accent color of the UiKit Theme Please refer to the code  below :

```java
__ initialize Palette class
Palette palette = Palette.getInstance(this);
palette.accent(getResources().getColor(R.color.green));
```



![](https://uploads.developerhub.io/prod/x9W8/qjlob9hl984g5j5rabwf45eox78g92pa1deb2zviai1y73xcjzafl3rh5pozz42w.png)

> similarly to change other Color of Theme you can refer to the above mentioned method.

### **Typography**

Typography contain methods which is use to change default Text Style from the Theme as per user need.

| Methods | Description | 
| ---- | ---- | 
| setHeading(int heading) | Use to set **Heading** text Appearance. | 
| setName(int name) | Use to set **Name** text Appearance. | 
| setTitle1(int title1) | Use to set **Title 1** text Appearance. | 
| setTitle2(int title2) | Use to set **Title 2** text Appearance. | 
| setSubtitle1(int subtitle1) | Use to set **Subtitle 1** text Appearance. | 
| setSubtitle2(int subtitle2) | Use to set **Subtitle 2** text Appearance. | 
| setText1(int text1) | Use to set **Text 1**  text Appearance. | 
| setText2(int text2) | Use to set **Text 2** text Appearance. | 
| setCaption1(int caption1) | Use to set **Caption 1** text Appearance. | 
| setCaption2(int caption2) | Use to set **Caption 2** text Appearance. | 


To change Name TextStyle of the UiKit Theme Please refer to the code  below :

```java
Typography typography = Typography.getInstance();
typography.setName(R.style.font);
```



![](https://uploads.developerhub.io/prod/x9W8/aa7x0s1zdkicmwzg8rqdb3p57f74sqevd1h2filvhwya0ti29ax7rl94or93u2jc.png)

> similarly to change other Text Style of Theme you can refer to the above mentioned method.