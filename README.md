# kotlin学习笔记

1、环境安装（Android Studio2.2.2）：

步骤1：安装kotlin插件；

File --> Settings --> Plugins --> Install JetBrains plugin --> 搜索kotlin --> install

步骤2：自动为项目配置kotlin。

Tools --> kotlin --> configure kotlin in project

就这么简单的两步就可以愉快的跟kotlin玩耍了，嘎嘎。

官方文档：http://kotlinlang.org/docs/tutorials/kotlin-android.html

中文翻译：https://www.kotlincn.net/docs/tutorials/kotlin-android.html

注：据说Android studio3.0默认安装了插件哦！


2、Android扩展插件

这个插件非常爽，妈妈再也不用担心我写一堆findView了。

步骤1：启用扩展插件

在模块的gradle文件里加上以下语句即可

    apply plugin: 'kotlin-android-extensions'


步骤2：导入布局 import kotlinx.android.synthetic.main.＜布局＞.*

好比如我的布局是activity_splash

    import kotlinx.android.synthetic.main.activity_splash.*

例子：
activity_splash.xml

    <?xml version="1.0" encoding="utf-8"?>
    <RelativeLayout
        xmlns:android="http://schemas.android.com/apk/res/android"
        xmlns:tools="http://schemas.android.com/tools"
        android:id="@+id/activity_splash"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context="com.example.jack.kotlin_demo.SplashActivity">

        <TextView
            android:id="@+id/textView"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"/>

    </RelativeLayout>

SplashActivity.java

    package com.example.jack.kotlin_demo

    import android.os.Bundle
    import android.support.v7.app.AppCompatActivity
    import kotlinx.android.synthetic.main.activity_splash.*

    class SplashActivity : AppCompatActivity() {

        override fun onCreate(savedInstanceState: Bundle?) {
            super.onCreate(savedInstanceState)
            setContentView(R.layout.activity_splash)
            textView.text = getString(R.string.hi)
        }
    }
