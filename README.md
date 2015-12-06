# Menu-navigation
# hình ảnh Demo
![screenshot from 2015-12-06 12 56 33](https://cloud.githubusercontent.com/assets/10550810/11611986/591d04b6-9c19-11e5-90c6-6ca1fcb1ffe5.png)
![screenshot from 2015-12-06 12 56 43](https://cloud.githubusercontent.com/assets/10550810/11611987/6812023c-9c19-11e5-8d02-9d5f1fff239d.png)

`   `
#values
### style.xml
```XML
<resources>

    <!-- Base application theme. -->
    <style name="AppTheme" parent="Theme.AppCompat.Light.NoActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/colorPrimary</item>
        <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
        <item name="colorAccent">@color/colorAccent</item>
    </style>

    <style name="ToolbarTheme" parent="AppTheme">
        <item name="android:textColorPrimary">@android:color/white</item>
        <item name="android:textColorSecondary">@android:color/white</item>
    </style>

    <style name="NavigationViewTheme" parent="AppTheme">
        <item name="textAppearanceListItem">@style/TextAppearance.AppCompat.Body2</item>
    </style>

</resources>


```
###color.xml
```XML
<resources>
    <color name="colorPrimary">#3F51B5</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
</resources>
```
###attrs.xml
```XML
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <bool name="fitsSystemWindows">true</bool>
    <dimen name="navigation_drawer_header_margin">24dp</dimen>
    <dimen name="status_bar_kitkat_height">0dp</dimen>
    <dimen name="status_bar_lollipop_height">0dp</dimen>
    <dimen name="status_bar_margin_top">0dp</dimen>

</resources>
```
#layout
###main.xml
```XML
<?xml version="1.0" encoding="utf-8"?>
<android.support.v4.widget.DrawerLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/navigation_drawer_layout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:fitsSystemWindows="@bool/fitsSystemWindows">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <FrameLayout
            android:layout_width="match_parent"
            android:layout_height="@dimen/status_bar_kitkat_height"
            android:background="?colorPrimary" />

        <FrameLayout
            android:layout_width="match_parent"
            android:layout_height="@dimen/status_bar_lollipop_height"
            android:background="?colorPrimaryDark" />

    </LinearLayout>

    <FrameLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="@dimen/status_bar_margin_top">

        <FrameLayout
            android:id="@+id/fragment"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

        <android.support.v7.widget.Toolbar
            android:id="@+id/toolbar"
            android:layout_width="match_parent"
            android:layout_height="?actionBarSize"
            android:background="?attr/colorPrimary"
            android:elevation="4dp"
            app:popupTheme="@style/ThemeOverlay.AppCompat.Light"
            app:theme="@style/ToolbarTheme" />

    </FrameLayout>

    <android.support.design.widget.NavigationView
        android:id="@+id/navigation_view"
        android:layout_width="wrap_content"
        android:layout_height="match_parent"
        android:layout_gravity="start"
        android:fitsSystemWindows="@bool/fitsSystemWindows"
        app:headerLayout="@layout/header"
        app:menu="@menu/navigation"
        app:theme="@style/NavigationViewTheme" />

</android.support.v4.widget.DrawerLayout>
```
###header.xml
```XML
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="192dp"
    android:gravity="bottom"
    android:theme="@style/ThemeOverlay.AppCompat.Dark">

    <ImageView


        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="@drawable/logo"
        android:scaleType="centerCrop" />

    <ImageView
        android:layout_width="64dp"
        android:id="@+id/Logo"
        android:layout_height="64dp"
        android:layout_marginLeft="16dp"
        android:layout_marginTop="@dimen/navigation_drawer_header_margin"
        android:scaleType="centerCrop"
         />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="52dp"
        android:layout_gravity="left|bottom"
        android:gravity="center"
        android:orientation="vertical"
        android:paddingBottom="8dp"
        android:paddingLeft="16dp"
        android:paddingRight="16dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:gravity="center_vertical"
            android:text="Le tan loc"

            android:textAppearance="@style/TextAppearance.AppCompat.Body2"
            android:id="@+id/us" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:gravity="center_vertical"
            android:text="nks.loclt#gmail.com"
            android:textAppearance="@style/TextAppearance.AppCompat.Body1" />
    </LinearLayout>
</FrameLayout>

```
#menu
###navigation.xml
```XML
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

    <group android:checkableBehavior="single">
        <item
            android:id="@+id/item_navigation_drawer_inbox"
            android:checked="true"
            android:icon="@drawable/ic_launcher"
            android:title="Inbox" />
        <item
            android:id="@+id/item_navigation_drawer_starred"
            android:icon="@drawable/ic_launcher"
            android:title="Starred" />
        <item
            android:id="@+id/item_navigation_drawer_sent_mail"
            android:icon="@drawable/ic_launcher"
            android:title="Sent mail" />
        <item
            android:id="@+id/item_navigation_drawer_drafts"
            android:icon="@drawable/ic_launcher"
            android:title="Drafts" />
    </group>

    <item android:title="Subheader">
        <menu>
            <item
                android:id="@+id/item_navigation_drawer_settings"
                android:icon="@drawable/ic_launcher"
                android:title="Settings" />
            <item
                android:id="@+id/item_navigation_drawer_help_and_feedback"
                android:icon="@drawable/ic_launcher"
                android:title="Help and feedback" />
        </menu>
    </item>

</menu>
```
###menu_main.xml
``` 
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">

</menu>

```
##* Phần Java  *
#main.java
```java
package com.loc.template;

import android.app.FragmentTransaction;
import android.support.design.internal.NavigationMenuItemView;
import android.support.design.widget.NavigationView;
import android.support.v4.app.FragmentManager;
import android.support.v4.view.GravityCompat;
import android.support.v4.widget.DrawerLayout;
import android.support.v7.app.ActionBar;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;
import android.support.v7.widget.Toolbar;
import android.util.Log;
import android.view.Menu;
import android.view.MenuItem;
import android.view.View;
import android.widget.ImageView;
import android.widget.TextView;

import com.loc.template.Untils.CircleTransform;
import com.loc.template.Untils.CircleTransformWhite;
import com.squareup.picasso.Picasso;

import butterknife.Bind;
import butterknife.ButterKnife;

public class MainActivity extends AppCompatActivity {

    DrawerLayout drawerLayout;
    Toolbar toolbar;
    ActionBar actionBar;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        InitactionBar();
        Iniview();

    }

    public void InitactionBar() {
        toolbar = (Toolbar) findViewById(R.id.toolbar);
        setSupportActionBar(toolbar);
        actionBar = getSupportActionBar();
        actionBar.setTitle("loc");
        actionBar.setHomeAsUpIndicator(R.drawable.ic_menu_white_36dp);
        actionBar.setDisplayHomeAsUpEnabled(true);

    }

    NavigationView navigationView;

    public void Iniview() {

//        Picasso.with(this).load(R.drawable.loc).transform(new CircleTransformWhite()).into(User);

//

        navigationView = (NavigationView) findViewById(R.id.navigation_view);
        drawerLayout = (DrawerLayout) findViewById(R.id.navigation_drawer_layout);

        View v = navigationView.getHeaderView(0);
            ImageView img =(ImageView)v.findViewById(R.id.Logo);

        Picasso.with(this).load(R.drawable.loc).placeholder(R.drawable.loc).transform(new CircleTransform()).into(img);
        if (navigationView != null) {
            setupNavigationDrawerContent(navigationView);
        }

        setupNavigationDrawerContent(navigationView);

        setFragment(0);

    }


    @Override
    public boolean onCreateOptionsMenu(Menu menu) {
        // Inflate the menu; this adds items to the action bar if it is present.
        getMenuInflater().inflate(R.menu.main, menu);
        return true;
    }

    @Override
    public boolean onOptionsItemSelected(MenuItem item) {
        switch (item.getItemId()) {
            case android.R.id.home:
                drawerLayout.openDrawer(GravityCompat.START);
                return true;
        }
        return super.onOptionsItemSelected(item);
    }

    /// thuw hien click
    public void setFragment(int position) {
        FragmentManager fragmentManager;
        FragmentTransaction fragmentTransaction;
        switch (position) {
            case 0:
//                fragmentManager = getSupportFragmentManager();
//                fragmentTransaction = fragmentManager.beginTransaction();
//                InboxFragment inboxFragment = new InboxFragment();
//                fragmentTransaction.replace(R.id.fragment, inboxFragment);
//                fragmentTransaction.commit();
                break;
            case 1:
//                fragmentManager = getSupportFragmentManager();
//                fragmentTransaction = fragmentManager.beginTransaction();
//                StarredFragment starredFragment = new StarredFragment();
//                fragmentTransaction.replace(R.id.fragment, starredFragment);
//                fragmentTransaction.commit();
                break;
        }
    }

    private void setupNavigationDrawerContent(NavigationView navigationView) {
        navigationView.setNavigationItemSelectedListener(
                new NavigationView.OnNavigationItemSelectedListener() {
                    @Override
                    public boolean onNavigationItemSelected(MenuItem menuItem) {
//                        switch (menuItem.getItemId()) {
//                            case R.id.item_navigation_drawer_inbox:
//                                menuItem.setChecked(true);
//                                setFragment(0);
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                return true;
//                            case R.id.item_navigation_drawer_starred:
//                                menuItem.setChecked(true);
//                                setFragment(1);
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                return true;
//                            case R.id.item_navigation_drawer_sent_mail:
//                                menuItem.setChecked(true);
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                return true;
//                            case R.id.item_navigation_drawer_drafts:
//                                menuItem.setChecked(true);
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                return true;
//                            case R.id.item_navigation_drawer_settings:
//                                menuItem.setChecked(true);
//                                Toast.makeText(MainActivity.this, "Launching " + menuItem.getTitle().toString(), Toast.LENGTH_SHORT).show();
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                Intent intent = new Intent(MainActivity.this, SettingsActivity.class);
//                                startActivity(intent);
//                                return true;
//                            case R.id.item_navigation_drawer_help_and_feedback:
//                                menuItem.setChecked(true);
//                                Toast.makeText(MainActivity.this, menuItem.getTitle().toString(), Toast.LENGTH_SHORT).show();
//                                drawerLayout.closeDrawer(GravityCompat.START);
//                                return true;
//                        }
                        return true;
                    }
                });
    }
}




```

