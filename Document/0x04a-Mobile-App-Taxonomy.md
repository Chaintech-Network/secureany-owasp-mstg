# Mobile Application Taxonomy

The term "mobile application" or "mobile app" refers to a self-contained computer program designed to execute on a mobile device. Today, the Android and iOS operating systems cumulatively comprise [more than 99% of the mobile OS market share](https://www.idc.com/promo/smartphone-market-share/os). Additionally, mobile Internet usage has surpassed desktop usage for the first time in history, making mobile browsing and apps the [most widespread kind of Internet-capable apps](https://www.idc.com/promo/smartphone-market-share/os).

> In this guide, we'll use the term "app" as a general term for referring to any kind of application running on popular mobile OSes.

In a basic sense, apps are designed to run either directly on the platform for which they’re designed, on top of a smart device’s mobile browser, or using a mix of the two. Throughout the following chapter, we will define characteristics that qualify an app for its respective place in mobile app taxonomy as well as discuss differences for each variation.

## Native App

Mobile operating systems, including Android and iOS, come with a Software Development Kit (SDK) for developing apps specific to the OS. Such apps are referred to as _native_ to the system for which they have been developed. When discussing an app, the general assumption is that it is a native app implemented in a standard programming language for the respective operating system - Objective-C or Swift for iOS, and Java or Kotlin for Android.

Native apps inherently have the capability to provide the fastest performance with the highest degree of reliability. They usually adhere to platform-specific design principles (e.g. the [Android Design Principles](https://developer.android.com/design "Android Design Principles")), which tends to result in a more consistent user interface (UI) compared to _hybrid_ or _web_ apps. Due to their close integration with the operating system, native apps can directly access almost every component of the device (camera, sensors, hardware-backed key stores, etc.).

Some ambiguity exists when discussing _native apps_ for Android as the platform provides two development kits - the Android SDK and the Android NDK. The SDK, which is based on the Java and Kotlin programming language, is the default for developing apps. The NDK (or Native Development Kit) is a C/C++ development kit used for developing binary libraries that can directly access lower level APIs (such as OpenGL). These libraries can be included in regular apps built with the SDK. Therefore, we say that Android _native apps_ (i.e. built with the SDK) may have _native_ code built with the NDK.

The most obvious downside of _native apps_ is that they target only one specific platform. To build the same app for both Android and iOS, one needs to maintain two independent code bases, or introduce often complex development tools to port a single code base to two platforms. The following frameworks are an example of the latter and allow you to compile a single codebase for both Android and iOS.

- [Xamarin](https://dotnet.microsoft.com/apps/xamarin "Xamarin")
- [Google Flutter](https://flutter.dev/ "Google Flutter")
- [React Native](https://reactnative.dev/ "React Native")

Apps developed using these frameworks internally use the APIs native to the system and offer performance equivalent to native apps. Also, these apps can make use of all device capabilities, including the GPS, accelerometer, camera, the notification system, etc. Since the final output is very similar to previously discussed _native apps_, apps developed using these frameworks can also be considered as _native apps_.

## Web App

Mobile web apps (or simply, _web apps_) are websites designed to look and feel like a _native app_. These apps run on top of a device’s browser and are usually developed in HTML5, much like a modern web page. Launcher icons may be created to parallel the same feel of accessing a _native app_; however, these icons are essentially the same as a browser bookmark, simply opening the default web browser to load the referenced web page.

Web apps have limited integration with the general components of the device as they run within the confines of a browser (i.e. they are "sandboxed") and usually lack in performance compared to native apps. Since a web app typically targets multiple platforms, their UIs do not follow some of the design principles of a specific platform. The biggest advantage is reduced development and maintenance costs associated with a single code base as well as enabling developers to distribute updates without engaging the platform-specific app stores. For example, a change to the HTML file for a web app can serve as viable, cross-platform update whereas an update to a store-based app requires considerably more effort.

## Hybrid App

Hybrid apps attempt to fill the gap between _native_ and _web apps_. A _hybrid app_ executes like a _native app_, but a majority of the processes rely on web technologies, meaning a portion of the app runs in an embedded web browser (commonly called "WebView"). As such, hybrid apps inherit both pros and cons of _native_ and _web apps_.

A web-to-native abstraction layer enables access to device capabilities for _hybrid apps_ not accessible to a pure _web app_. Depending on the framework used for development, one code base can result in multiple apps that target different platforms, with a UI closely resembling that of the original platform for which the app was developed.

Following is a non-exhaustive list of more popular frameworks for developing _hybrid apps_:

- [Apache Cordova](https://cordova.apache.org/ "Apache Cordova")
- [Framework 7](https://framework7.io/ "Framework 7")
- [Ionic](https://ionicframework.com/ "Ionic")
- [jQuery Mobile](https://jquerymobile.com/ "jQuery Mobile")
- [Native Script](https://www.nativescript.org/ "Native Script")
- [Onsen UI](https://onsen.io/ "Onsen UI")
- [Sencha Touch](https://www.sencha.com/products/touch/ "Sencha Touch")

## Progressive Web App

Progressive Web Apps (PWA) load like regular web pages, but differ from usual web apps in several ways. For example it's possible to work offline and access to mobile device hardware is possible, that traditionally is only available to native mobile apps.

PWAs combine different open standards of the web offered by modern browsers to provide benefits of a rich mobile experience. A Web App Manifest, which is a simple JSON file, can be used to configure the behavior of the app after "installation".

PWAs are supported by Android and iOS, but not all hardware features are yet available. For example Push Notifications, Face ID on iPhone X or ARKit for augmented reality is not available yet on iOS. An overview of PWA and supported features on each platform can be found in a [Medium article from Maximiliano Firtman](https://medium.com/@firt/progressive-web-apps-on-ios-are-here-d00430dee3a7 "Progressive Web Apps on iOS are here").

## What's Covered in the Mobile Testing Guide

Throughout this guide, we will focus on apps for Android and iOS running on smartphones. These platforms are currently dominating the market and also run on other device classes including tablets, smartwatches, smart TVs, automotive infotainment units, and other embedded systems. Even if these additional device classes are out of scope, you can still apply most of the knowledge and testing techniques described in this guide with some deviance depending on the target device.

Given the vast amount of mobile app frameworks available it would be impossible to cover all of them exhaustively. Therefore, we focus on _native_ apps on each operating system. However, the same techniques are also useful when dealing with web or hybrid apps (ultimately, no matter the framework, every app is based on native components).
