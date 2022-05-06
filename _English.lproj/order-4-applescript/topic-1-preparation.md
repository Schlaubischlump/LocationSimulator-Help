---
title: Preparation
group: AppleScript
order: 0
---

Currently the AppleScript support is limited. It does not support interacting with the user interface directly besides the standard commands such as *close window*, *activate*, *quit*. Instead you can interact with the underlying devices directly. Changes to a device are not reflected in the user interface. Therefore you might consider running *LocationSimulator* without a user interface. Start *LocationSimulator* from the command line using the `--no-ui` flag to run in a headless state, without menubar, dock icon or window. Using the AppleScript API is still possible. If *LocationSimulator* is installed in the `/Applications` folder you can execute the following command to start in a headless state: 

``` sh
/Applications/LocationSimulator.app/Contents/MacOS/LocationSimulator --no-ui
```

