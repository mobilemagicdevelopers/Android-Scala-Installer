### Android Scala Installer
This is an Android application that lets you install the Scala 2.9.1 standard library onto your rooted Android device as a set of shared libraries.
Once these are installed to your development device, you can forgo packaging the Scala library with your application and running Proguard. The Proguard
step alone takes about 1.5-2 minutes on my machine.  It's a huge time-saver.

This is *ONLY* useful for development purposes as it lets you build Android applications without including the Scala library
in your APK.  When packaging your application for general consumption (e.g. the Android Market) you should not rely on Scala being pre-installed
or require users to use this application.

Your device must be rooted to do use this application.

### Building

This project uses SBT and jberkel's [android-plugin](https://github.com/jberkel/android-plugin).  You can build the apk with "sbt android:package-debug".  For more detials on using the android-plugin see its [Getting Started](https://github.com/jberkel/android-plugin/wiki/getting-started) guide.

### Android Market

You can find this application on the Android Market [here](https://market.android.com/details?id=com.mobilemagic.scalainstaller)

### Referencing the library

To reference the libraries in your application during development you should add the following lines to the application element in your AndroidManifest.xml


    <uses-library android:name="scala_actors-2.9.1"/>
    <uses-library android:name="scala_collection-2.9.1"/>
    <uses-library android:name="scala_immutable-2.9.1"/>
    <uses-library android:name="scala_library-2.9.1"/>
    <uses-library android:name="scala_mutable-2.9.1"/>


### Credits

The majority of the work done for this was completed by [Johannes Rudolph](https://github.com/jrudolph)
This application is essentially a line-for-line conversion of his work to Scala with a few minor additions.
