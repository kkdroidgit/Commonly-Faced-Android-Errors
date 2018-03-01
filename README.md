# Commonly-Faced-Android-Errors
A curated list of commonly faced issues and error messages and how to solve them. The list is specifically designed for Android Basics Course on Udacity as a part of Google Challenge India Scholarship, though most errors are general in nature and can occur while developing for any application.

## 1. Cannot Resolve Symbol (-R) or R.layout.main Cannot Be Found
Sometimes Android Studio is unable to generate `R.java` file correctly. `R.java` is a dynamically generated class, created during build process to dynamically identify all assets (from strings to android widgets to layouts), for usage in our java classes.

## Solution :-
The most optimum solution is to Clean Build the Project and Sync again. <b> Build > Clean Project </b> would normally resolove this issue. Also check for the import statements and see if the package name is correct. If there is some modifications in directories and files you would do <b> File > Invalidate Caches / Restart > Invalidate and Restart </b>. 


## 2. Getting MainActivity.kt instead of MainActivity.java
`.kt` is for Kotlin file extension. This is not an error but if you are following the Android Basics Course code, it will generate errors. The Course follows Java programming language, instead of Kotlin. This appears when you check `Include Kotlin` option in the begining of your Project Creation.

## Solution :-
It is recommended that to close this project and create a new one. Refractoring `MainActivity.kt` to `MainActivity.java` might do the trick, but you need to change every Java file thereafter. Since Kotlin is 100% interoperable with Java, you can incorporate it seamlessly into your existing app. So if you are following this course, create a new project.


