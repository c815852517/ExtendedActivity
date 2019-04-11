# 实验四——扩展的Activity
## 实验环境
Android Studio 3.2
## 主要代码
### MainActivity.java:
```
package com.example.acer.expandactivity;

import android.preference.PreferenceActivity;
import android.preference.PreferenceFragment;
import android.support.v7.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends PreferenceActivity {

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        addPreferencesFromResource(R.xml.mypreference);
    }
}

```

### mypreference.xml:
```
<?xml version="1.0" encoding="utf-8"?>
<PreferenceScreen xmlns:android="http://schemas.android.com/apk/res/android">
    <PreferenceCategory
        android:title="in-line preference"
        android:key="firstpre">
        <CheckBoxPreference
            android:key="checkbox"
            android:title="CheckBox preference"
            android:summary="This is a checkbox"
            android:defaultValue="true"/>
    </PreferenceCategory>
    <PreferenceCategory
        android:title="Dialog-based preferences"
        android:key="secondpre">
        <EditTextPreference
            android:key="edittext"
            android:title="Edit text preference"
            android:summary="An example that uses an edit text dialog"
            android:dialogTitle="Enter your favorite animal">
        </EditTextPreference>
        <ListPreference
            android:key="listpre"
            android:title="List preference"
            android:summary="An example that uses a list dialog"
            android:dialogTitle="Choose one"
            android:entries="@array/tests"
            android:entryValues="@array/tests_value">
        </ListPreference>
    </PreferenceCategory>
    <PreferenceCategory
        android:title="Launch preferences"
        android:key="thirdpre">
        <PreferenceScreen
            android:key="intent_prescreen"
            android:title="Screen preference"
            android:summary="Shows another screen of preferences">
            <CheckBoxPreference
                android:key="toggle_pre"
                android:title="Toglle preferences"
                android:summary="Preference that is on the next screen but same hierarchy">
            </CheckBoxPreference>
        </PreferenceScreen>
        <PreferenceScreen
            android:title="intent preference"
            android:summary="Launches an Activity from an Intent">
            <intent android:action="android.intent.action.VIEW"
                android:data="http://www.baidu.com"></intent>
        </PreferenceScreen>
    </PreferenceCategory>
    <PreferenceCategory
        android:title="Preference attributes"
        android:key="fouthpre">
    <CheckBoxPreference
        android:title="Parent checkbox preference"
        android:key="parent_check_pre"
        android:summary="This is visually a parent">
    </CheckBoxPreference>
    <CheckBoxPreference
        android:title="Child checkbox preference"
        android:key="child_check_pre"
        android:summary="This is visually a child"
        android:dependency="parent_check_pre">
    </CheckBoxPreference>
    </PreferenceCategory>
</PreferenceScreen>
```

### 实验界面截图
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/main.jpg)
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/1.jpg)
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/2.jpg)
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/3.jpg)
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/4.jpg)
![](https://github.com/c815852517/ExtendedActivity/blob/master/app/src/5.jpg)
