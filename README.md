# Menu-navigation

![screenshot from 2015-12-06 12 56 33](https://cloud.githubusercontent.com/assets/10550810/11611986/591d04b6-9c19-11e5-90c6-6ca1fcb1ffe5.png)
![screenshot from 2015-12-06 12 56 43](https://cloud.githubusercontent.com/assets/10550810/11611987/6812023c-9c19-11e5-8d02-9d5f1fff239d.png)
# Menu-navigation

![screenshot from 2015-12-06 12 56 33](https://cloud.githubusercontent.com/assets/10550810/11611986/591d04b6-9c19-11e5-90c6-6ca1fcb1ffe5.png)
![screenshot from 2015-12-06 12 56 43](https://cloud.githubusercontent.com/assets/10550810/11611987/6812023c-9c19-11e5-8d02-9d5f1fff239d.png)
`   `
#values
## style.xml
```
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
##color.xml
```
<resources>
    <color name="colorPrimary">#3F51B5</color>
    <color name="colorPrimaryDark">#303F9F</color>
    <color name="colorAccent">#FF4081</color>
</resources>
```
##attrs.xml
``` 
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
##main.xml
```
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

