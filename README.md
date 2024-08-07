## Watch the Tutorial

[![Watch the video](https://img.youtube.com/vi/_pPntgcs5rM/maxresdefault.jpg)](https://youtu.be/pPntgcs5rM)


### Step 1: Organizing our Files

![Organize this file](https://cdn.hashnode.com/res/hashnode/image/upload/v1722970571156/ff4c7287-704c-4900-9c17-fc1c42ce4251.png)

1. **Prepare the following files to stay organized:**
    
    * **Java Files:**
        
        `AddPage`
        
        `HomePage`
        
        `ProfilePage`
        
        `MainActivity`
        
    * **XML Layout Files:**
        
        `activity_add_page.xml`
        
        `activity_homepage.xml`
        
        `activity_main.xml`
        
        `activity_profile_page.xml`
        
    * **XML Menu:**
        
        `bottom_navigation_menu.xml`
        
    * **XML Color:**
        
        `bottom_navigation_selector.xml`
        

By following these steps, we can ensure that our project files are well-organized, making our development process more efficient

### Step 2: Add Assets or Icon

![Add Assets or Icon](https://cdn.hashnode.com/res/hashnode/image/upload/v1722971540085/1a30d804-ca93-4eec-b88d-05521b63258b.png)

* To add an asset, right-click on the `drawable` folder, then select `New > Vector Assets`.
    
* Configure the vector asset by choosing clip art, search for a home icon, and click OK to finish.
    

### Step 3: Code the bottom\_navigation\_menu.xml

![Code the bottom\_navigation\_menu.xml](https://cdn.hashnode.com/res/hashnode/image/upload/v1722972024678/ee01b2c3-6325-4b1a-8c0e-28c31b925e6b.png)

* * <mark>Add three icons for Home, Add, and Profile.</mark>
        
* **Instructions:**
    
    * Remember to include all three icons in the code.
        
    * You can refer back to this page if you need to check the details again.
        

Here's the sample code snippet to add the icons:

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">


    <item
        android:id="@+id/nav_home"
        android:icon="@drawable/baseline_home_24"
        android:title="Home" />

    <item
        android:id="@+id/nav_add"
        android:icon="@drawable/baseline_add_24"
        android:title="Add" />

    <item
        android:id="@+id/nav_profile"
        android:icon="@drawable/baseline_person_24"
        android:title="Profile" />

</menu>
```

### Step 4: Code the bottom\_navigation\_selector.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_checked="true" android:color="#282828"/>
    <item android:color="#928D8D"/>
</selector>
```

This file ensures that the bottom navigation icons change color when selected or not selected, improving user interaction and visual feedback.

### Step 5: Code the activity\_main.xml

![Code the activity\_main.xml](https://cdn.hashnode.com/res/hashnode/image/upload/v1722972708364/f182e514-ecc2-471a-9d2c-62db59905bdc.png)

This layout sets up a main activity screen with a white background, a container for fragments above a bottom navigation bar. The navigation bar has icons and text with color states defined by the `bottom_navigation_selector.xml` and references the menu items from `bottom_navigation_menu.xml`.

#### Just Remember:

* **Remember the IDs** used in the layout for referencing in your code:
    
    * `fragment_container` for the FrameLayout.
        
    * `bottom_navigation` for the BottomNavigationView.
        

Here is the code snippet for `activity_main.xml`:

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    tools:context=".MainActivity">

    <FrameLayout
        android:id="@+id/fragment_container"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_above="@id/bottom_navigation" />

    <com.google.android.material.bottomnavigation.BottomNavigationView
        android:id="@+id/bottom_navigation"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:background="#FFFFF5"
        app:layout_alignParentBottom="true"
        app:itemIconTint="@color/bottom_navigation_selector"
        app:itemTextColor="@color/bottom_navigation_selector"
        app:menu="@menu/bottom_navigation_menu" />

</RelativeLayout>
```

### Step 6: Code the fragment\_add\_page.xml, fragment\_homepage.xml, fragment\_profile\_page.xml

<mark>fragment_add_page.xml</mark>

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    tools:context=".fragments.AddPage">


    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Add Page"
        android:layout_centerInParent="true"
        android:textSize="40sp"
        android:textColor="@color/black"
        />

</RelativeLayout>
```

<mark>fragment_homepage.xml</mark>

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    tools:context=".fragments.HomePage">


    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Homepage"
        android:layout_centerInParent="true"
        android:textSize="40sp"
        android:textColor="@color/black"
        />

</RelativeLayout>
```

<mark>fragment_profile_page.xml</mark>

```xml
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/white"
    tools:context=".fragments.ProfilePage">


    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Profile Page"
        android:layout_centerInParent="true"
        android:textSize="40sp"
        android:textColor="@color/black"
        />

</RelativeLayout>
```

### Step 7: Code the AddPage, Homepage and Profile Page Class

<mark>AddPage.java</mark>

```java
package com.thirdydacoder.bottomnavigationbar.fragments;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.fragment.app.Fragment;
import com.thirdydacoder.bottomnavigationbar.R;

public class AddPage extends Fragment {

    View view;
    
    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        view = inflater.inflate(R.layout.fragment_add_page, container, false);
        
        return view;
    }
   
}
```

<mark>Homepage.java</mark>

```java
package com.thirdydacoder.bottomnavigationbar.fragments;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.fragment.app.Fragment;
import com.thirdydacoder.bottomnavigationbar.R;

public class HomePage extends Fragment {

    View view;
    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        view = inflater.inflate(R.layout.fragment_homepage, container, false);
        return view;
    }
}
```

<mark>ProfilePage.java</mark>

```java
package com.thirdydacoder.bottomnavigationbar.fragments;

import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import androidx.annotation.NonNull;
import androidx.annotation.Nullable;
import androidx.fragment.app.Fragment;
import com.thirdydacoder.bottomnavigationbar.R;

public class ProfilePage extends Fragment {

    View view;

    @Nullable
    @Override
    public View onCreateView(@NonNull LayoutInflater inflater, @Nullable ViewGroup container, @Nullable Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        view = inflater.inflate(R.layout.fragment_profile_page, container, false);

        return view;
    }

}
```

### Step 8: Code the MainActivity

Explain the code:

```java
BottomNavigationView bottomNav = findViewById(R.id.bottom_navigation);
bottomNav.setSelectedItemId(R.id.nav_home);
bottomNav.setOnItemSelectedListener(navListener);

Fragment selectedFragment = new HomePage();

getSupportFragmentManager().beginTransaction().replace(R.id.fragment_container,
        selectedFragment).commit();
```

These lines of code set up the `BottomNavigationView`, select the Home item by default, and set up a listener for navigation item selections. The default fragment (`HomePage`) is displayed in the `fragment_container` when the activity starts.

---

```java
private NavigationBarView.OnItemSelectedListener navListener =
        item -> {
            int itemId = item.getItemId(); /* obtain the selected item ID from your source */
            Fragment selectedFragment = null;

            if (itemId == R.id.nav_home) {
                selectedFragment = new HomePage();
            } else if (itemId == R.id.nav_add) {
                selectedFragment = new AddPage();
            } else if (itemId == R.id.nav_profile) {
                // Handle the profile case
                selectedFragment = new ProfilePage();

            } else {
                selectedFragment = new HomePage();
            }
            getSupportFragmentManager().beginTransaction().replace(R.id.fragment_container, selectedFragment).commit();
            return true;
        };
```

This listener handles navigation item selections. It checks the selected item's ID and sets the corresponding fragment (`HomePage`, `AddPage`, or `ProfilePage`). It then replaces the current fragment in the `fragment_container` with the selected fragment and commits the transaction.

Main Activity whole code:

```java
package com.thirdydacoder.bottomnavigationbar;

import android.os.Bundle;

import androidx.appcompat.app.AppCompatActivity;
import androidx.fragment.app.Fragment;

import com.google.android.material.bottomnavigation.BottomNavigationView;
import com.google.android.material.navigation.NavigationBarView;
import com.thirdydacoder.bottomnavigationbar.fragments.AddPage;
import com.thirdydacoder.bottomnavigationbar.fragments.HomePage;
import com.thirdydacoder.bottomnavigationbar.fragments.ProfilePage;

public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);

        setContentView(R.layout.activity_main);

        BottomNavigationView bottomNav = findViewById(R.id.bottom_navigation);
        bottomNav.setSelectedItemId(R.id.nav_home);
        bottomNav.setOnItemSelectedListener(navListener);

        Fragment selectedFragment = new HomePage();

        getSupportFragmentManager().beginTransaction().replace(R.id.fragment_container,
                selectedFragment).commit();

    }

    private NavigationBarView.OnItemSelectedListener navListener =
            item -> {
                int itemId = item.getItemId(); /* obtain the selected item ID from your source */
                Fragment selectedFragment = null;

                if (itemId == R.id.nav_home) {
                    selectedFragment = new HomePage();
                } else if (itemId == R.id.nav_add) {
                    selectedFragment = new AddPage();
                } else if (itemId == R.id.nav_profile) {
                    // Handle the profile case
                    selectedFragment = new ProfilePage();

                } else {
                    selectedFragment = new HomePage();
                }
                getSupportFragmentManager().beginTransaction().replace(R.id.fragment_container, selectedFragment).commit();
                return true;
            };

}
```

### **OUTPUT**

![A mobile app interface with a bottom navigation bar containing three icons labeled "Home," "Add," and "Profile." The screen shows the text "Homepage" in the center.](https://cdn.hashnode.com/res/hashnode/image/upload/v1722974179816/8b3cbbcf-9ec7-4a76-b035-6fa9cc30807b.gif)

Thank you for following this tutorial on creating a Bottom Navigation View in Android Java.

If you found this helpful, please subscribe to my YouTube channel for more tutorials.

[Thirdy DaCoder — YouTube](https://www.youtube.com/@ThirdyDaCoder)

If you want the complete source code, you can find it on GitHub. Make sure to star the repository if you like it!

%[https://github.com/thirdygayares/BottomNavigationBar.git] 

Buy me a coffee

[https://www.buymeacoffee.com/thirdygayares](https://www.buymeacoffee.com/thirdygayares)

Please check out my other content and connect with me on various platforms:

* YouTube: [@thirdydacoder](https://www.youtube.com/@ThirdyDaCoder)
    
* Github: [thirdygayares](https://github.com/thirdygayares)
    
* LinkedIn: [Jose Gayares III](https://www.linkedin.com/in/thirdygayares/)
    
* Facebook Page: [Thirdy Dacoder](https://www.facebook.com/thirdydacoder)
    
* Website: [thirdygayares.com](https://thirdygayares.com/)
    
* Website : [thirdygraphics.com](https://www.thirdygraphics.com/)
    

Feel free to reach out with any questions or feedback. Happy coding!
