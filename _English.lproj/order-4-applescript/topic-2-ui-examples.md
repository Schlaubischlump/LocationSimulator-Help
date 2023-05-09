---
title: UI Examples
group: AppleScript
order: 1
---

**Toggle the sidebar**

This example toggles the visibility of the sidebar of the window.

``` applescript
tell application "LocationSimulator"
    set win to first window
    set isCollapsed to sidebar is collapsed of win
    tell win to set sidebar is collapsed to (not isCollapsed)
end tell
```

---

**Select a device**

This example selects the first device in the sidebar of the window.

``` applescript
tell application "LocationSimulator"
    set win to first window
    set myDevice to first device
    tell win to set selected device to myDevice
end tell
```

---

**Change device location**

This example changes the location of the currently selected device to a default location. If no device is selected you will get an error. After waiting 2 seconds the location is reset to the original location.

``` applescript
tell application "LocationSimulator"
    set win to first window
    set myMap to map view of win
    tell myMap
        -- {latitude, longitude}
        set current location to {37.3305976, -122.0265794}
        delay 2.0
        reset location
    end tell
end tell
```

**Move device location**

This example defines a function you can use to move left, right, up, down or in the direction of heading. 

``` applescript
on moveLocation(direction)
    tell application "LocationSimulator"
        set myMap to map view of first window
        tell myMap
            if direction is "up" then
                set heading to 0
            else if direction is "left" then
                set heading to 90
            else if direction is "down" then
                set heading to 180
            else if direction is "right" then
                set heading to 270
            end if

            move in direction of heading
        end tell
    end tell
end moveLocation
...

my moveLocation("left")
```

**Toggle automatic movement**

This example toggles the automatic movement feature on or off.  

``` applescript
tell application "LocationSimulator"
    set myMap to map view of first window
    tell myMap
        set isAutoMoving to move automatically
        set move automatically to (not isAutoMoving)
    end tell
end tell
```

**Navigation**

The following example shows you how to calculate and start a new navigation from the current location to a destination location. The program will wait until the navigation is finished.

``` applescript
set destination to {37.3345976, -122.0265794}

on toggleAutoFocus()
    tell application "LocationSimulator"
        set myMap to map view of first window
        tell myMap
            set isAutoFocusing to focus automatically
            set focus automatically to (not isAutoFocusing)
        end tell
    end tell
end toggleAutoFocus

tell application "LocationSimulator"
    set myMap to map view of first window
    tell myMap
        -- toggle the auto focus on and off to zoom in
        my toggleAutoFocus()
        set myRoute to calculate route from current location to destination
        follow route myRoute
        my toggleAutoFocus()

        -- wait until we followed the route to the end
        -- if auto reverse is on this is an endless loop
        repeat while follows route
            delay 1.0
        end repeat
    end tell
end tell
```

**Request location change from user**

This last example asks the user to either teleport or navigate to a destination location. It waits until the user has selected an option. If a new navigation is started, it will also wait until the navigation is finished.

``` applescript
set destination to {37.3345976, -122.0265794}

tell application "LocationSimulator"
    set myMap to map view of first window
    tell myMap
        request location change to destination

        -- wait until the user has interacted with the alert
        repeat while shows user alert
            delay 0.5
        end repeat

        -- wait until a possible navigation has started
        delay 2.0

        -- if the user started a navigation we wait until its finished
        repeat while follows route
            delay 0.5
        end repeat
    end tell
end tell
```