---
title: Preparation
group: AppleScript
order: 0
---

You can interact with LocationSimulator using two different ways: 

**UI mode**

*LocationSimulator*  provides a set of suits to automate its UI. You can change the location, start navigations, change the device selection and much more. You can find the full set of functionality by looking at the library of *LocationSimulator* in *ScriptEditor*.

---

**Headless mode**

You can also use *LocationSimulator* to directly interact with devices bypassing the UI completely. That is, changes to a device are not reflected in the user interface. Therefore you might consider running *LocationSimulator* without even starting the user interface. Start *LocationSimulator* from the command line using the `--no-ui` flag to run in a headless state, without menubar, dock icon or window. Using the AppleScript API is still possible. If *LocationSimulator* is installed in the `/Applications` folder you can execute the following command to start it in a headless state: 

``` sh
/Applications/LocationSimulator.app/Contents/MacOS/LocationSimulator --no-ui
```

