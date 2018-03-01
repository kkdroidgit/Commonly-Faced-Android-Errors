# Commonly-Faced-Android-Errors

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
Gradle is a build system and is improvised form of other build systems. It is based on JVM. You must have seen build.gradle file(s) in your project. That is where you can write scripts to automate your tasks. The code you saw in these files is Groovy code. If you write `System.out.println("Hello Gradle!");` then it will print on your console. Gradle doesn't correspond to errors. Read more at https://stackoverflow.com/questions/16754643/what-is-gradle-in-android-studio

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
