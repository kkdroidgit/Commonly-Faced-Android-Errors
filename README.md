# Commonly-Faced-Android-Errors-and-Issues

<img src="https://i.imgur.com/Pf8CTIc.jpg" width="350">

A curated list of commonly faced issues and error messages and how to solve them. The list is specifically designed for Android Basics Course on Udacity as a part of Google Challenge India Scholarship, though most errors are general in nature and can occur while developing for any application.


## 1. Cannot Resolve Symbol (-R) or R.layout.main Cannot Be Found
Sometimes Android Studio is unable to generate `R.java` file correctly. `R.java` is a dynamically generated class, created during build process to dynamically identify all assets (from strings to android widgets to layouts), for usage in our java classes.

## Solution :-
The most optimum solution is to Clean Build the Project and Sync again. <b> Build > Clean Project </b> would normally resolove this issue. Also check for the import statements and see if the package name is correct. If there is some modifications in directories and files you would do <b> File > Invalidate Caches / Restart > Invalidate and Restart </b>. 


## 2. Getting MainActivity.kt instead of MainActivity.java
`.kt` is for Kotlin file extension. This is not an error but if you are following the Android Basics Course code, it will generate errors. The Course follows Java programming language, instead of Kotlin. This appears when you check `Include Kotlin` option in the begining of your Project Creation.

## Solution :-
It is recommended that to close this project and create a new one. Refractoring `MainActivity.kt` to `MainActivity.java` might do the trick, but you need to change every Java file thereafter. Since Kotlin is 100% interoperable with Java, you can incorporate it seamlessly into your existing app. So if you are following this course, create a new project.


## 3. What is Gradle? Does Gradle == Error?
Gradle can be bit confusing for a new Android developer. Sometimes people make it synonymous to error. 

## Solution :-
<b>tl;dr : </b>
Gradle is a system to build Android Applications.

Read on:-
Gradle is a build system and is improvised form of other build systems. It is based on JVM. You must have seen build.gradle file(s) in your project. That is where you can write scripts to automate your tasks. The code you saw in these files is Groovy code. If you write `System.out.println("Hello Gradle!");` then it will print on your console. Gradle doesn't correspond to errors. [Read more](https://stackoverflow.com/questions/16754643/what-is-gradle-in-android-studio)

## 4. Error:CreateProcess error=216, This version of %1 is not compatible with the version of Windows you're running. Check your computer's system information and then contact the software publisher

## Solution :-
Install JDK 1.8. Then in Android Studio navigate to File-> Project Structure-> SDK Location, select your directory where the JDK is located.Click OK and you are good to go.


## 5. Failed to find Build Tools revision 26.0.2

<img src="https://i.imgur.com/TFGKwJe.png">


## Solution :-
Click on `Install missing platform(s) and sync project` in Messages Gradle Sync tab and download the build tools.
Or alternatively,
under `$PROJECT_ROOT/app/build.gradle` folder open `build.gradle` file and add `buildToolsVersion '27.0.3'`

```
android {

    compileSdkVersion 27
    buildToolsVersion '27.0.3' //add or change that line

    defaultConfig {
        applicationId "com.example.com"
        minSdkVersion 16
        targetSdkVersion 27
       // More config
    }
    // more
    
} 
```


## 6. Incorrect placement of Views even after applying correct attributes

<img src="https://i.imgur.com/kI6SyuY.png" width="360">

This is not an error but just a project setup tip. Android Studio now uses Constraint Layout as root viewgroup in default templates. But at the time the course videos were recorded this wasn't the case. Therefore, if you copy paste some xml code from instructor notes to your activity's xml file, the appearance is not the same.

## Solution :-
Go to your activity_name.xml file and replace `android.support.constraint.ConstraintLayout` with `RelativeLayout`. In most cases, you can find this in the second line of the file just after `<?xml version="1.0" encoding="utf-8"?>`.

## 7. Disabling Landscape Mode/Orientation Changes for your app

If you have enabled auto-rotation feature on your phone then your app might look completely different in the landscape mode. So how can you disable the auto-rotate feature in Android?

## Solution :-
Navigate to `AndroidManifest.xml` and in the activity declaration add the following :

```
<activity android:name=".MainActivity"
    android:screenOrientation="portrait" />
```
This forces your application to be in potrait mode only. If you want this for whole application check this [post](https://stackoverflow.com/questions/6745797/how-to-set-entire-application-in-portrait-mode-only/9784269#9784269)



## 8. Android Studio not Detecting Redmi Devices Even after USB Debugging Enabled

## Solution :-

- Go to Settings > Additional settings > Developer options
- Disable the "Turn on MUI optimization"
- Reboot your phone

Alternatively,
- Install Mi PC Suite
- Connect Your Phone
- Go to Permission in Settings and click `Install Via USB`



## 9. Session 'app': Error Launching activity

## Solution :-
- If app was installed via `USB debugging` on a real device, then it gets installed for all the **User Accounts** present on the device. So, if you uninstalled app from **Current User Account** then, next time on a new installation of same app `(by pressing run button from Android Studio)`, you might get this error: ***Session 'app': Error Launching activity***.

- To resolve this, [Switch to other User Accounts](https://support.google.com/nexus/answer/2865483?hl=en) and delete that app from all other **User Accounts** including **Guest Account.**

- If that doesn't help, remove `.gradle` and `.idea` directories manually by switching to [Project View](https://developer.android.com/studio/projects/index.html) (Look for `The Android Project View` in this webpage), and later `Rebuild Project` and `Re-run`. 



## 10. Gradle Build showing AAPT2 Error : "com.android.tools.aapt2.Aapt2Exception: AAPT2 error: check logs for details"

## Solution :-
- Go to Gradle Scripts
- Left click on build.gradle (Module.app)
- Type in android.enableAapt2=false

![alt text](https://i.stack.imgur.com/lWyT2.png)



## 11. layout_weight property not working

## Solution :-
- Parent Linear Layout's _height_ and _width_ should be set to "match parent"

<img src="http://i67.tinypic.com/dors5j.jpg" width="450">



## 12. For giving border radius to buttons, shape.xml needs to be formed in "drawable" folder.
       not in "values" folder.

## Solution :-
- Right click on drawable folder
- Make a new drawable resource file
- Name it as shape.xml

<img src="http://i65.tinypic.com/mbspyr.png" width="450">



## 13. Gradle failed to resolve library in Android studio.

## Solution:-
You go File->Settings->Gradle Look at the "Offline work" inbox, if it's checked you uncheck and try to sync again. [Source](https://stackoverflow.com/questions/28493470/gradle-failed-to-resolve-library-in-android-studio)



## 14. Removing Hard Coded Strings from your XML
       
## Solution:-
Make a separate strings.xml resource file in Android Studio and use that.
Set the cursor inside the text you want to extract (here the text is the title “Cancel”) and hit ALT + Enter  and select “Extract string resource”:

<img src="http://envyandroid.com/content/images/2014/03/extract1.png" width="450">

Give your resource a describing name and hit “Ok”:

<img src="http://envyandroid.com/content/images/2014/03/extract2.png" width="450">
          
          Your string has now been moved to the strings.xml file.



## 15. OutofMemoryError

## Solution:-
This is thrown when your app is making memory requests that the system can’t meet.

There are many potential causes of an OutOfMemoryError, but some of the most common include holding onto references for too long, loading large bitmaps, and memory leaks. The fix will vary depending on the cause of your particular OutOfMemoryError, so you’ll need to track down the problem before you can work out the solution. For example, if the error turns out to be related to large, memory-hogging bitmaps, then a possible fix might be to load the bitmap at a reduced scale.

Android Studio comes with various tools that can help you analyze the way your app is using memory, including Memory Monitor, Allocation Tracker, HPROF Viewer, and the Android Device Monitor’s ‘Heap’ tab.

## A general approach to solving all these kinds of errors can be given as in the below chart:-

<img src="https://s3.amazonaws.com/codementor_content/2016-Nov/android-app-wont-run-infographic.png" width="450">



## 16. NullPointerException on setOnClickListener()

## Solution:-

NullPointerException appears when the method setOnClicklistener() cannot find the View element that you are trying to call this method on. Kindly check if you have written correct View element name in the initialization statement and there are no errors in the XML view.


## 17. Cmake_Error in Androidstudio

<img src="https://discourse-cdn-sjc3.com/udacity/uploads/default/optimized/4X/4/a/c/4ac1f9cfc8115fa6b2fcb2ec9693ec7ad658ba89_1_690x387.png" width="450">

## Solution:-

cmake error you get because of chossing c++ language option at time of making project.If you want to get rid of it,there are two way;
1.eiher at time of new project ,you deselect c++ option;
2.or ,you can download full package of cmake;
your problem will be resolve with it.

To download the Cmake.
Just follow this -
File > Settings > Appearance and behavior> System Settings > Android SDK  
Here in SDk tools —> Cmake —> download it and install.

# Credits

- kartikohri1712 - [GitHub](https://github.com/kartikohri1712)
- Tirth Patel - [Github](https://github.com/piedcipher)
- Divya Thakur - [Github](https://github.com/divyathakur24)
- Ikram Mohammad - [Github](https://github.com/Ikramkhan786)
- Ojasvi Bhargava -[Github](https://github.com/ojasvibhargava)
- Niraj Tiwary -[Github](https://github.com/tiwaryniraj)

