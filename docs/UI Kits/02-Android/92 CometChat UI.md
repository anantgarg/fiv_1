In this guide you will learn how to create a tabbed layout component using [bottom navigation](https://m2.material.io/components/bottom-navigation#using-tabs) to use widgets like [CometChatUsersWithMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/users-with-messages), [CometChatGroupsWithMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/groups-with-messages) and [CometChatConversationsWithMessages](https://www.cometchat.com/docs/v3/android-v4-uikit/users-with-messages) simultaneously.

> You need to create an account with CometChat to use the components> > Also, ensure initializing CometChatUIKit first and logging in correctly before trying to render any component from the UI Kit package> > Please make sure you have followed our [Integration](https://www.cometchat.com/docs/v3/flutter-v4-uikit/integration) guidelines.

Without further ado, let's get into how we can build this thing.

- First, lets create a Activity, lets call it CometChatUiActivity and add the following code into the xml file of the activity

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http:__schemas.android.com_apk_res_android"
    xmlns:app="http:__schemas.android.com_apk_res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <LinearLayout
        android:id="@+id_container"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:orientation="vertical" _>

    <com.google.android.material.bottomnavigation.BottomNavigationView
        android:id="@+id_bottomNavigationView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@android:color_white"
        android:minHeight="60dp"
        app:itemIconTint="@color_selected_item"
        app:itemTextAppearanceActive="@style_Subtitle2"
        app:itemTextColor="@color_selected_item"
        app:menu="@menu_bottom_nav_menu_item"
        app:tabIndicator="@null"
        app:tabMinWidth="72dp"
        app:tabPaddingBottom="0dp"
        app:tabPaddingEnd="0dp"
        app:tabPaddingStart="0dp"
        app:tabPaddingTop="0dp" _>
<_LinearLayout>
```



Now lets create menu that need to be shown on a Bottom navigation view. To create a **Menu**, first, create a **Menu Directory** **by clicking on the_** **app**_**-&gt;**_ **_ res**(right-click) -&gt;_ _**New**_ _-&gt;_ _**Android Resource Directory**_ _and select_ _**Menu**_ _in the_ _**Resource Type**_._

![](https://uploads.developerhub.io/prod/x9W8/l9edombe1wtdvkqfyipwq2qk1clm4p1k2h0iuxev0j1pmnwh91sg6tl3lmz18ub4.png)

To create a **Menu Resource File** , click on the **app** -&gt; **res** -&gt; **menu**(right-click) -&gt; **New** -&gt; **Menu Resource File** and name it **bottom_nav_menu_item**.

![](https://uploads.developerhub.io/prod/x9W8/zb9hggzii3w01gdsa6je0kaw0qy7ebduke22io84jj2159dflf39t22ofkhcmjtq.png)

 add the below code in **bottom**_**_**_**nav_menu_item**

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http:__schemas.android.com_apk_res_android">
    <item
        android:id="@+id_chat"
        android:title="@string_chats"
        android:icon="@drawable_cc_ic_chats"_>
    <item
        android:id="@+id_user"
        android:title="@string_users"
        android:icon="@drawable_cc_ic_users"_>
    <item
        android:id="@+id_group"
        android:title="@string_groups"
        android:icon="@drawable_cc_ic_groups"_>
<_menu>
```



similarly we need to create a **color directory** and need to add a color file with the below code init 

```xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http:__schemas.android.com_apk_res_android">
    <item android:state_checked="true" android:color="@color_primary" _>
    <item android:color="@color_accent400"  _>
<_selector>
```



Now create 4 Fragments and load `CometChatConversationsWithMessages`,  `CometChatUsersWithMessages`, `CometChatGroupsWithMessages`and `CometChatCallHistoryWithDetails`   individually in each of them.

ConversationsWithMessagesFragment.java

```java
public class ConversationsWithMessagesFragment extends Fragment {

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        __ Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_conversation_with_messages, container, false);
    }
}
```



```java
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http:__schemas.android.com_apk_res_android"
    xmlns:tools="http:__schemas.android.com_tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".fragments.conversations.ConversationsWithMessagesFragment">

    <com.cometchat.chatuikit.conversationswithmessages.CometChatConversationWithMessages
        android:id="@+id_conversationWithMessages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>

<_FrameLayout>
```



UsersWithMessagesFragment.java

```java
public class UsersWithMessagesFragment extends Fragment {


    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        __ Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_users_with_messages, container, false);
    }
}
```



```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http:__schemas.android.com_apk_res_android"
    xmlns:tools="http:__schemas.android.com_tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".fragments.users.UsersWithMessagesFragment">

    <com.cometchat.chatuikit.userswithmessages.CometChatUsersWithMessages
        android:id="@+id_userWithMessages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>

<_FrameLayout>
```



GroupsWithMessagesFragment.java

```java
public class GroupsWithMessagesFragment extends Fragment {

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        __ Inflate the layout for this fragment
        return inflater.inflate(R.layout.fragment_groups_with_messages, container, false);
    }
}
```



```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http:__schemas.android.com_apk_res_android"
    xmlns:tools="http:__schemas.android.com_tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".fragments.groups.GroupsWithMessagesFragment">

    <com.cometchat.chatuikit.groupswithmessages.CometChatGroupsWithMessages
        android:id="@+id_groupWithMessages"
        android:layout_width="match_parent"
        android:layout_height="match_parent" _>

<_FrameLayout>
```



Now in CometChatUiActivity add the below code.

```java
import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.Fragment;

import com.cometchat.pro.javasampleapp.R;
import com.cometchat.pro.javasampleapp.fragments.calls.CallHistoryWithDetailsFragment;
import com.cometchat.pro.javasampleapp.fragments.conversations.ConversationsWithMessagesFragment;
import com.cometchat.pro.javasampleapp.fragments.groups.GroupsWithMessagesFragment;
import com.cometchat.pro.javasampleapp.fragments.users.UsersWithMessagesFragment;
import com.google.android.material.bottomnavigation.BottomNavigationView;

public class CometChatUiActivity extends AppCompatActivity {

    private BottomNavigationView bottomNavigationView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_comet_chat_ui);

        bottomNavigationView = findViewById(R.id.bottomNavigationView);
        loadFragment(new ConversationsWithMessagesFragment());
        bottomNavigationView.setOnItemSelectedListener(item -> {
            switch (item.getItemId()) {
                case R.id.chat:
                    loadFragment(new ConversationsWithMessagesFragment());
                    break;
                case R.id.user:
                    loadFragment(new UsersWithMessagesFragment());
                    break;
                case R.id.group:
                    loadFragment(new GroupsWithMessagesFragment());
                    break;
            }
            return true;
        });
        bottomNavigationView.setSelectedItemId(R.id.chat);
    }

    private void loadFragment(Fragment fragment) {
        if (fragment != null)
            getSupportFragmentManager().beginTransaction().replace(R.id.container, fragment).commit();
    }
}
```



Yippee 🎉 !!! We have successfully built a CometChatUi. 🎉