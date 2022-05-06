---
title: Examples
group: AppleScript
order: 1
---

**List all devices**

This example lists all currently connected devices. Each device is identified by its UUID.

``` applescript
tell application "LocationSimulator"
    -- device id F0218413-D540-4EA6-A391-C59660EDD625
```

---

**Get device information**

This example prints some basic information for every currently available device, such as the name or the version number.

``` applescript
tell application "LocationSimulator"
        -- F0218413-D540-4EA6-A391-C59660EDD625 : iPhone SE (3rd generation) : iPhone OS : 15.4 : true
```

---

**Change device location**

This example shows you how to change the device location of every currently connected real iOS device to a hardcoded location. Before spoofing the location of a real iOS device you need to make sure, that the *DeveloperDiskImage* is uploaded. You can do this by calling the `pair` method. For simulator devices `pair` is a NOP. This function requires *LocationSimulator* to already have a valid *DeveloperDiskImage* for your device and iOS version. No automatic download is performed.

``` applescript
tell application "LocationSimulator"
```