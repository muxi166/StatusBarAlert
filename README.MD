
[![Android Arsenal]( https://img.shields.io/badge/Android%20Arsenal-Status%20Bar%20Alert-green.svg?style=flat )]( https://android-arsenal.com/details/1/7037 )
 [![Download](https://api.bintray.com/packages/fede987/status-bar-alert/status-bar-alert/images/download.svg) ](https://bintray.com/fede987/status-bar-alert/status-bar-alert/_latestVersion)

<img src="https://github.com/fede87/StatusBarAlert/raw/master/status_bar_alert_demo.gif" width="330" height="600" />

## What is this?

This is a small library inspired by Telegram X status bar new alert written in Kotlin.
It can show custom message with optional indeterminate progress in status bar area.
Optional autohide feature can be tweaked with custom duration.
When showing, status bar alert kindly hides status bar's icon with SYSTEM_UI_FLAG_LOW_PROFILE flag mode, if available from os.

## Supported devices

This lib is supported by every device with a SDK level of at least 14 (Android 4+. On Android 4.x the alert will be drawn below the status).

<b>Android X required for v1.1.0 and above, otherwise use old version v1.0.2.</b>

## Quick walkthrough

### Gradle


Add this line to your app's dependencies:

```
implementation 'com.fede987:status-bar-alert:1.2.0'
```

### Quick Sample

Show a new status bar alert:

```
val statusBarAlertview: StatusBarAlertView = StatusBarAlert.Builder(this@MainActivity)
                       .autoHide(true)
                       .withDuration(100)
                       .showProgress(true)
                       .withText("autohide!")
                       .withAlertColor(R.color.colorPrimaryDark)
                       .withTextColor(R.color.colorAccent)
                       .withIndeterminateProgressBarColor(R.color.colorAccent)
                       .withTypeface(typeface)
                       .build()
                       
                       
//update status bar alert view text at any time:
statusBarAlertView.updateText("UPDATED!!")
//or:
statusBarAlertView.updateText(R.string.updated)
 
 
// show indeterminate progress:
statusBarAlertView.showIndeterminateProgress()
 
// hide indeterminate progress:
statusBarAlertView.hideIndeterminateProgress()
 
```

Hide all status bar alerts for current activity with an optional "on hidden" callback:

```
StatusBarAlert.hide(this@MainActivity) {
    // onHidden callback
    Toast.makeText(this@MainActivity.applicationContext, "Alert has been hidden.", Toast.LENGHT_SHORT).show()
}

// or just call:

StatusBarAlert.hide(this@MainActivity)

```

## License

    Copyright 2018 Federico Marin

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.



 
