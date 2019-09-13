## What is the latest version of Android ?

4.4 – 4.4.4	**KitKat**	2013
5.0 – 5.1.1	**Lollipop**	2014
6.0 – 6.0.1	**Marshmallow**	2015
7.0 – 7.1.2	**Nougat**	2016
8.0 – 8.1	**Oreo**	2017
9.0	**Pie**	2018

## What is an Activity?

An Activity **is the screen representation** of an application in Android.

An activity is implemented as a subclass of Activity class as follows:

    public class MainActivity extends Activity {
    }

## Explain Android Architecture.

 - Linux Kernel
 - Libraries
 - Android Framework
 - Android Applications

## What is APK format?

The APK file or Android application package is the compressed file format 

## What is the life cycle of android activity?

 - **onCreate() :**  **the activity is created.**
 - **onStart():** ***the activity becomes visible*** to the user.
 - **onResume():** The activity is in the foreground and **the user can interact with it.**

 - **onPause():** Activity is partially obscured by another activity.

 - **onStop():** The activity is completely hidden and not visible to the user.
 - **onDestroy():** Activity is destroyed and removed from the memory.

## Define intents in Android. What are the different types of intents?

An Intent is an “intention” to do an action.  An intent is a messaging object you can use to request an action from another app component.

Methods are used to deliver intents to different components:

    context.startActivity() – To start an activity
    context.startService() – To start a service
    context.sendBroadcast() – To deliver a broadcast


## What is the difference between an implicit intent and explicit intent?

 - Implicit Intent **is used whenever you are performing an action.**
   For example, send email, SMS, dial number or you can use a Uri to
   specify the data type. For example:

    Intent i = new Intent(ACTION_VIEW,Uri.parse("http://www.edureka.co")); 
    startActivity(i);

 - Explicit, on the other hand, helps you **to switch from one activity
   to another activity(often known as the target activity)**.  **It is
   also used to pass data using putExtra method and retrieved by other
   activity by getIntent().getExtras() methods.**

    Intent i = new Intent(this, Activitytwo.class); #ActivityTwo is the target component
    i.putExtra("Value1","This is ActivityTwo"); 
    i.putExtra("Value2","This Value two for ActivityTwo"); 
    startactivity(i);

## What is an Android Framework?

It is a set of APIs that allows developers to write apps and has the following components:

 - **Services	Components** 
 - **Intent	Objects**
 - **Activities**	
 - **Content Providers**	Components that enable users to access data within an app such as audio, video, images, contact information, etc.
 - **Others**	App widgets and Processes and Threads

## What is Google Android SDK? What are the tools placed in android SDK?

 - Android Emulator
 - DDMS – Dalvik Debug Monitoring Services
 - AAPT – Android Asset Packaging tool
 - ADB – Android debug bridge

## What is a Toast? Write its syntax.

Toast notification is a message that pops up on the window.

    Toast.makeText(ProjectActivity.this, "Your message here", Toast.LENGTH_LONG).show();


## What is an ANR? What are some measures you can take to avoid ANR?

ANR stands for ‘Application Not Responding’. **This dialogue is displayed if the main thread in the application has been unresponsive for a long time and in the following conditions:**

 - When there is no response to an input event after 5 seconds.
 - When a broadcast receiver is not done executing within 10 seconds

## How will you pass data to sub-activities?

**We can use Bundles to pass data to sub-activities.**
There are like HashMaps that and take trivial data types. These Bundles transport information from one Activity to another

    Bundle b=new Bundle();
    b.putString("Email","abc@xyz.com");
    i.putExtras(b); // where I is intent

## What is the use of WebView in Android?

WebView is a view that display web pages inside your application. 

## What are the different kinds of context in Android?

Context defines the current state of an App. **Context provides access to creating new activity instance, access databases, start a service, etc.** There is a base class ApplicationContext, and subclasses for components: Activity, Service.

## Explain in brief about the important file and folder when you create a new app?

**App** – It describes the fundamental characteristics of the app and defines each of its components.
**java** – This contains the .java source files for your project.
**res** – It is a directory for files that define your app’s user interface. 
**Gradle** 


## What are the different storage methods in Android?

 - Shared Preferences – Store private primitive data in key-value pairs
 - Internal Storage – Store private data on the device memory
 - External Storage – Store public data on the shared external storage
 - SQLite Databases – Store structured data in a private database

## What is a Service? How is it implemented?

A service in android is a background process which is used to perform long-running operations. 

Local: This service is accessed from within the application.
Remote – This service is accessed remotely from other applications running on the same device.

public class MyService extends Service {
}


##  Explain Folder, File & Description of Android Apps

**src:** contains the .java source files for your project.

**gen:** contains the .R file, a compiler-generated file that references all the resources found in your project.

**bin:** contains the Android package files .apk built by the ADT during the build process and everything else needed to run an Android application.

**res/drawable-hdpi:** this is a directory for drawable objects that are designed for high-density screens.

**res/layout:** this is a directory for files that define your app’s user interface.

**res/values:** this is a directory for other various XML files that contain a collection of resources, such as strings and colors definitions.

**AndroidManifest.xml:** this is the manifest file which describes the fundamental characteristics of the app and defines each of its components.


## How does Manifest file plays an integral role in App development?

Manifest file plays an integral role as it provides the essential information about your app to the Android system, which the system must have before it can run any of the app’s code. Manifest file performs various tasks such as:



## What is the difference between a fragment and an activity?

Activity is typically a single, focused operation that a user can perform such as dial a number, take a picture, send an email, view a map etc.

Fragment is a modular section of an activity, with its own lifecycle and input events, and which can be added or removed at will. Also, a fragment’s lifecycle is directly affected by its host activity’s lifecycle i.e. when the activity is paused, so are all fragments in it, and when the activity is destroyed, so are all of its fragments.



## What is DDMS?

DDMS stands for Dalvik Debug Monitor Server. It gives the following array of debugging features:

Port forwarding services
Screen capture on the device
Thread and heap information
Logcat
Incoming call and SMS spoofing
Network traffic tracking
Location data spoofing



## What are the containers?

Containers, holds objects and widgets together, depending on which specific items are needed and in what particular arrangement that is wanted. Containers may hold labels, fields, buttons, or even child containers, as examples.

## What is an Android Runtime?

Android Runtime consists of Dalvik Virtual machine and Core Java libraries.
DVM is optimized for low processing power and low memory environments.
Unlike JVM, the Dalvik Virtual Machine doesn’t run .class files, instead it runs .dex files.

## Name the four essential states of an activity.

**Active** – if the activity is at the foreground
**Paused** – if the activity is at the background and still visible
**Stopped** – if the activity is not visible and therefore is hidden or obscured by another activity
**Destroyed** – when the activity process is killed or completed terminated

## What are the core building blocks of android?

Activity 
Content Provider
Service
Broadcast Receivers

## What are the dialog boxes that are supported in Android? Android supports four dialog boxes:

AlertDialog
 ProgressDialog
DatePickerDialog
TimePickerDialog



## What is Dalvik Virtual Machine (DVM)?

Dalvik is the name of Android’s virtual machine.
The Dalvik VM is an interpreter-only virtual machine that executes files in the Dalvik Executable (.dex) format.

## What is a content provider? How is it implemented?

Content providers manage access to a structured set of data. It is the standard interface that connects data in one process with code running in another process.

  

  public class MyContentprovider extends ContentProvider {
     public void onCreate(){
      }
   }

 

## What is the significance of the .dex files?

Android programs are compiled into ‘.dex’ (Dalvik Executable) files, which are zipped into a single .apk file on the device.


## What does ADB stand for?

ADB stands for Android Debug Bridge. It is a command line tool that is used to communicate with the emulator instance. ADB can control your device over USB from a computer, copy files back and forth, install and uninstall apps, run shell commands, and more.


## What is AIDL? What are the datatypes supported by AIDL ?
AIDL stands for Android Interface Definition Language.

## Which components are necessary for a New Android project?

**manifest:** It contains xml file.
**build/:** It contains build output.
**src/:** It contains the code and resource files.
**res/:** It contains bitmap images, UI Strings and XML Layout i.e. all non-code resources.
**assets/:** It contains a file which should be compiled into a .apk file.

## What is meant by Services?

Answer: Service is an Android component which runs in the background and acts independently. It does not provide any user interface.

Public class MainService extends Service
{
}

## How do you find memory leaks in the mobile app on Android platform?

Answer: Android Studio is using Android Device Manager (ADM), this ADM is used to detect the memory leaks in the Android platform.


## What are the different data storage options available on the Android platform?

**SharedPreference:** It stores data in XML files. It is the simplest way to store private data in the key-value pair.
**SQLite:** It stores structure data in the private database.
**Internal Storage:** It stores data in the device file system and any other app cannot read this data.
**External Storage:** Data is stored in the file system but it is accessible to all apps in the device



## Difference between AsyncTasks & Threads?

 - Thread should be used to separate **long running operations from main
   thread so that performance is improved.**
 - AsyncTask can be used to handle work items shorter than 5ms in
   duration. **With AsyncTask, you can update UI unlike java Thread.**

## What is Context?

A Context is a handle to the system; it provides services like resolving resources, obtaining access to databases and preferences, and so on. 

 - **Application Context:** This context is tied to the lifecycle of an
   application. The application context can be used where you need a
   context whose lifecycle is separate from the current context or when
   you are passing a context beyond the scope of an activity.
   
 - **Activity Context:** This context is available in an activity. This
   context is tied to the lifecycle of an activity. The activity context
   should be used when you are passing the context in the scope of an
   activity or you need the context whose lifecycle is attached to the
   current context.

## What is Armv7?

There are 3 CPU architectures in Android.

 - ARMv7 is the most common as it is optimised for battery consumption.
 - ARM64 is an evolved version of that that supports 64-bit
 - ARMx86, is the least used for these three, since it is not battery
   friendly.

## Why bytecode cannot be run in Android?

Android uses DVM (Dalvik Virtual Machine ) rather using JVM(Java Virtual Machine).


## Explain the build process in Android:

 - First step involves compiling the resources folder (/res) using the
   aapt (android asset packaging tool) tool. These are compiled to a
   single class file called R.java. This is a class that just contains
   constants.
 - Second step involves the java source code being compiled to .class
   files by javac, and then the class files are converted to Dalvik
   bytecode by the “dx” tool, which is included in the sdk ‘tools’. The
   output is classes.dex.
   
 - The final step involves the android apkbuilder which takes all the
   input and builds the apk (android packaging key) file.

## onSavedInstanceState() and onRestoreInstanceState() in activity?

**OnRestoreInstanceState()** - **When activity is recreated after it was previously destroyed, we can recover the saved state from the Bundle that the system passes to the activity.**

** onSaveInstanceState()** - is a method used to store data before pausing the activity.


## android manifest

    < manifest xmlns:android="http://schemas.android.com/apk/res/android"
        package="kchaou.uha.fr.event">
    
        < uses-permission android:name="android.permission.INTERNET" />
    
        < application
            android:allowBackup="true"
            android:icon="@mipmap/ic_launcher"
            android:label="@string/app_name"
            android:roundIcon="@mipmap/ic_launcher_round"
            android:supportsRtl="true"
            android:theme="@style/AppTheme">
            
            <activity android:name=".MainActivity">
                <intent-filter>
                    <action android:name="android.intent.action.MAIN" />
    
                    <category android:name="android.intent.category.LAUNCHER" />
                </intent-filter>
    
            < /activity>
            < activity android:name=".EventActivity" />
            < activity android:name=".ClientActivity"></activity>
        < /application>
    
    < /manifest>

## What is the AppCompatActivity?

AppCompatActivity is a specific type of activity that allows you to use the support library action bar features. 

## AsyncTask

AsyncTask<Void, Void, Void>
protected void onPreExecute()
protected Void doInBackground(Void... arg0)
protected void onPostExecute(Void result)

## class R

R.java is the dynamically generated class, created during build process to dynamically identify all assets (from strings to android widgets to layouts), for usage in java classes in Android app. 

## Fragments

The fragment callback methods are :

 - **onAttach()** is called when a fragment is connected to an activity.
 - **onCreate()** is called to do initial creation of the fragment.
 - **onCreateView()** is called by Android once the Fragment should inflate
   a view.
 - **onViewCreated()**  Any view setup should happen here. E.g., view
   lookups, attaching listeners.
 - **onActivityCreated()** is called when host activity has completed its
   onCreate() method.
 - **onStart()** is called once the fragment is ready to be displayed on
   screen
 - **onResume()** - Allocate “expensive” resources such as registering for
   location, sensor updates, etc.
 - **onPause()** - Release “expensive” resources. 
 - **onDestroyView()** is called when fragment's view is being destroyed,
   but the fragment is still kept around.
 - **onDestroy()** is called when fragment is no longer in use.
 - **onDetach()** is called when fragment is no longer connected to the
   activity.

## Files hierarchy

app -> manifest -> androidmanisfest.xml
    -> java -> MainActivity.java
    -> generatedjava -> R.java, BuildConfig.java
    -> res -> drawble
           -> layout
           -> mipmap
           -> values 
gradle scripts
-> build.gradle
-> settings.gradle

## values

## colors.xml

    < resources>
        < color name="colorPrimary">#008577< /color>
    < /resources>

## styles.xml

    < resources>
    
        < style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
            < item name="colorPrimary">@color/colorPrimary</item>
            < item name="colorPrimaryDark">@color/colorPrimaryDark</item>
            < item name="colorAccent">@color/colorAccent</item>
        < /style>
    
    < /resources>


## strings.xml

    < resources>
        < string name="app_name">event< /string>
    < /resources>

## menu.xml

    < resources>  
        < string-array name="spinnerItems">  
            < item>Gélule</item>  
            < item>Comprimé</item>  
            < item>Liquide</item>  
        < /string-array>
    < /resources>    


## components

## Button

**android : clickable = “bool”** set to false to disable the button
**android : id=”@+id/theID** unique ID for use in java code
**android : onClick=”function”** 
**android : text=”text”** text to put in the button

## ImageView

**android : id=”@+id/theID”** unique ID for use in java code
**android : src=”@drawable/img** image to put in the screen (must coreespond
to an image resource)

## EditText

**android : hint =”text”** gray text to show before user starts to type
**android : id=”@+id/theID** unique ID for use in java code
**android : inputTyp=”type”** what kind of input is being typed; number, phone, date, time,...
**android : lines=”int”** number of visible lines (rows) of input
**android : maxlines=”int”** max lines toallow user to type in the box
**android : text=”text”** intial text to put in box (default empty)
**android : textSizes=”size”** size of font to use (e.g. “20dp”)

## checkbox

**android : checked=”bool”** set to true to make it initially checked
**android : clickable=”bool”** set to false to disable the checkbox
**android : id=”@+id/the ID** unique ID for use in java code
**android : onClick=”function”**
**android : text=”text”** text to put next to the checkbox

## RadioButton

**android : checked=”bool”** set to true to make it initially checked
**android : clickable=”bool”** set to false to disable the button
**android : id=”@+id/the ID** unique ID for use in java code
**android : onClick=”function”** 
**android : text=”text”** text to put next to the button

## Spinner

**android : clickable=”bool”** set to false to disable the spinner
**android : id=”@+id/theID** unique ID for use in java code
**android : entries=”@array/array”** set of options to appear in spinner 
**android : prompt=”@string/text”** title text when dialog of choices pops up

## ScrollView

**android:layout_width="wrap_content"**
**android:layout_height="wrap_content"**

## ListView

## RecycleView

## Layout

 - FrameLayout 
 - LinearLayout 
 - GridLayouts 
 - RelativeLayout
 - ConstraintLayout

## Layout width/height

 - wrap_contant
 - match_parent
 - fill_parent

## Action Bar

● Action bar : top-level menu of app functions

## Menu


     public  boolean onCreateOptionsMenu(Menu menu) {
      getMenuInflater().inflate(R.menu.menu_main, menu);
      return  true;
      }
    

    public  boolean onOptionsItemSelected(MenuItem item) {
      int id = item.getItemId();
      switch (id){
       case R.id.item1:
     
     }
      }

**File: menu_main.xml**

    < menu  xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    tools:context="example.javatpoint.com.optionmenu.MainActivity">
    
    < item  android:id="@+id/item1" android:title="Item 1"/>
    < item  android:id="@+id/item2" android:title="Item 2"/>
    < item  android:id="@+id/item3" android:title="Item 3"
    app:showAsAction="withText"/>
    < /menu>


