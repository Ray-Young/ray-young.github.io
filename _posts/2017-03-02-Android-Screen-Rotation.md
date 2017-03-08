---
layout: post
date: 2017-03-02
title: Andoird Screen Rotation
comments: true
tags: [Android]
---

### Introduction
Basically (If we do not add any code), if we rotate the screen, the
previous activity will be automatically destroyed and the system will
adjust the screen automatically.

Of course, we want do more. Then we have this blog.

It will introduce you how to build another layout for landscape (or
portrait), how to tell the code not to destroy the previous activity,
and how to specify what to do after rotation.

Here we discuss onConfigChange

### Add landscape view
First, switch the view scope to project, just like the following photo

![view_scope][1]

Then right click res->Andoird Resource Directory, and config following
this

![landscape_config][2]

Change Resource type to layout, select orientation and choose screen
orientation to landscape.

Now we have a new folder layout-land and just copy the layout in
portrait to this folder, make adjustment for the layout you like.

Next step is change the code and let it know you would like to use
another layout when change orientation.

### Specify what to do after rotation
Add the following code to the activity you want to make rotation

```Java
    @Override
    public void onConfigurationChanged(Configuration newConfig) {
        super.onConfigurationChanged(newConfig);
        setContentView(R.layout.activity_main);

        // TODO

    }
```

It tells system that you want to use the corresponding layout after
config change (which is orientation change in the case)

Add what you want to do in the TODO part, Now when you rotate the
screen, system won't call onCreate, but call onConfigurationChanged

### Update Manifest
Add the following code to activity tag

```xml
android:configChanges="orientation|screenSize"
```

It works with onConfigurationChanged, which tells system do not destroy
the original activity after the configuration change.

### Save instance
There are many ways to save data, class member or savedInstance are
common ways, I used class member here. But for professional, I recommend
you use savedInstanceState, which is the build in API for Android.

### Summary
This is one way to rotate the screen and update the corresponding code
and layout in Android. Again there are many ways to realize the aim, so
take your own choice. I upload my sample project on
[github][3], just for your reference.

[1]: /assets/android_screen_rotation/1.png
[2]: /assets/android_screen_rotation/2.png
[3]: https://github.com/Ray-Young/Android/tree/master/HangmanGame
