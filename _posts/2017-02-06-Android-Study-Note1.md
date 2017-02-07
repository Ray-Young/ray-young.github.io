---
layout: post
title: Android Study Note - Layout Design and MultiThread
date: 2017-02-06
comments: true
tags: [Android]
---

### Introduction
Recently I am studying Android again, so many amazing changes since 2
years ago, it's worth stepping forward.

This post will introduce how to define your own style, how to design
layout and how to use multiThread to update Activity components.

### Define your own style

We can define our own style and use them to decorate our layout. To do
this, first go to the styles.xml, it locates at

```path
/res/values/styles.xml
```

Then we can start define our own style

```xml
<style name="TextStyle" parent="@android:style/TextAppearance">
        <item name="android:layout_width">wrap_content</item>
        <item name="android:layout_height">wrap_content</item>
        <item name="android:layout_centerHorizontal">true</item>
        <item name="android:layout_centerVertical">true</item>
</style>
```

Remember we have to inherit the parent
```xml
parent="@android:style/TextAppearance"
```
in the base class. The inheritance can be multi levels, you can start
the magic now!

### Design Layout

There are so many tags in android when starting layout design. Here I
will list some useful tags when design your own layout.

```xml
align clusters
```
enables you to use the relative layout greatly, you can explore it by
yourself. For example,

```xml
android:layout_alignBaselin
```
Make the target in the same line with the source

### Multi Thread
When we want to refresh or update some components in the activity
periodically (at a corresponding fast and automatic way, we need to use
a thread to do this). Because activity is used as a thread, it cannot
handle to much work, use another thread to handle extra big works seems the
best way ( also applied when download or update picture)

```Java
btnStart.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        Thread t = new Thread() {
            @Override
            public void run() {
                try {
                    while (!isInterrupted()) {
                        Thread.sleep(3000);
                        runOnUiThread(new Runnable() {
                            @Override
                            public void run() {
                                simulate(i);
                                i++;
                            }
                        });
                    }
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
            }
        };
        t.start();
    }
});
```

Add the previous code in the onCreate which start a new Thread to do the extera hard work. Define what you want the system do in the run function.

For complete code, you can refer [my github][1].

[1]: https://github.com/Ray-Young/Android_Study/tree/master/Lesson2
