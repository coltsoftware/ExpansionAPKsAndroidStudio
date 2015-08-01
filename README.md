Importing the google play expansion library to Android Studio isn't easy and the [documentation](http://developer.android.com/google/play/expansion-files.html) only tells you how to do it with Eclipse.

So this is a library of pre-imported projects, which were first loaded in to eclipse, then the project imported to Android Studio:

- Google Play APK Expansion Library rev. 3
- Google Play Licensing Library rev. 2

#Fixes

`my_fixes` branch contains patches to the original, which is found in `master`. I recommend using `my_fixes` branch.

##Zip file

###Patch file number

If the patch obb version number differed from main file obb version number (very likely) then the code did not find the patch file as it used the main file number to create the patch file name.

##Downloader library

###Flickering downloading notification

Seen when the application is restoring it's own obb file.
The notification builder wasn't reused, so a new notification was created at each progress step.

##Play licensing

###LVL crash on lollipop

> java.lang.IllegalArgumentException: Service Intent must be explicit: Intent { act=com.android.vending.licensing.ILicensingService }

Thanks to http://stackoverflow.com/questions/28305125/android-app-crashes-on-lollipop

