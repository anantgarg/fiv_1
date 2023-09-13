To add UI Kit module developer will need to follow the three basic steps.

Step 1- Download [UI Kit](https://github.com/cometchat-pro/android-chat-ui-kit)  library from Github

Step 2- To add **uikit** module developer needs to follow few steps:

      a. Right-click on **an app** and go to **Open Module Settings**

![](https://res.cloudinary.com/developerhub/image/upload/v1637063973/v2_5163/rtffkns2eo239ecwb8wk.png)

   b. Click on **+** and select **Import Gradle Project** from Create New Module Window and click **Next**.

![](https://res.cloudinary.com/developerhub/image/upload/v1637063990/v2_5163/zlqxxdrai5u1os3snwiz.png)

c. After that developer has to enter the path of **uikit** which he/she has downloaded and click on **Finish**.

![](https://res.cloudinary.com/developerhub/image/upload/v1637064030/v2_5163/kioycd8fduebbgtkozgv.png)

Step 3- After following these steps **uikit** is successfully added in the project. Now to integrate the **uikit** in project developer can either copy and paste the following in (app level) `build.gradle`.

```javascript
implementation project(path: ':uikit')
```



If the Library is added successfully, it will look like mentioned in the below image.

![](https://res.cloudinary.com/developerhub/image/upload/v1637064130/v2_5163/rcgebhrzvxttxtgrxpdg.png)

_**Next Steps**  [Configure UI Ki](https://www.cometchat.com/docs/java-chat-ui-kit/overview#configure-ui-kit-library)t_