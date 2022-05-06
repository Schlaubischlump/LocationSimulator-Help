---
title: Examples
group: AppleScript
order: 1
---

**List all devices**

This example lists all currently connected devices. Each device is identified by its UUID.

``` applescript
tell application "LocationSimulator"    set mydevices to get every device    log mydevices
    -- device id F0218413-D540-4EA6-A391-C59660EDD625end tell
```

---

**Get device information**

This example prints some basic information for every currently available device, such as the name or the version number.

``` applescript
tell application "LocationSimulator"    repeat with mydevice in every device        set |id| to id of mydevice        set |name| to name of mydevice        set product to productName of mydevice        set |version| to productVersion of mydevice        set isSim to simulator of mydevice        log |id| & " : " & |name| & " : " & product & " : " & |version| & " : " & isSim
        -- F0218413-D540-4EA6-A391-C59660EDD625 : iPhone SE (3rd generation) : iPhone OS : 15.4 : true    end repeatend tell
```

---

**Change device location**

This example shows you how to change the device location of every currently connected real iOS device to a hardcoded location. Before spoofing the location of a real iOS device you need to make sure, that the *DeveloperDiskImage* is uploaded. You can do this by calling the `pair` method. For simulator devices `pair` is a NOP. This function requires *LocationSimulator* to already have a valid *DeveloperDiskImage* for your device and iOS version. No automatic download is performed.

``` applescript
tell application "LocationSimulator"    repeat with mydevice in (every device whose simulator is false)        try            tell mydevice to pair        on error errorStr number errorNumber            log errorStr & " : " & errorNumber        end try		        tell mydevice to change location latitude 20.632784 longitude 18.007621        -- change location of mydevice latitude 20.632784 longitude 18.007621        delay 2        tell mydevice to reset location    end repeatend tell
```