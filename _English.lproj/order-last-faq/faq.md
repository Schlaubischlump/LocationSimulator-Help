---
title: FAQ
order: 1000
---

---

<details>
	<summary>How long does the spoofed location last before it is reset to the real device location ?</summary>
	<span markdown="1">The spoofed location will last forever unless you manually reset it. See ['Stop location spoofing'](../order-1-get-started/topic-3-spoof-location.html) for more details. Rebooting your iOS device or toggling location service on and off will also reset your spoofed location.</span>
</details>

---

<details>
	<summary>Does this application spoof the altitude value as well ?</summary>
	<span markdown="1">No the altitude value will not be changed. *Xcode* as well as *libimobiledevice* use the *com.apple.dt.simulatelocation* service provided by the uploaded DeveloperDiskImage. This service does not allow changing the altitude. If you want to change your altitude value you have to jailbreak your device.</span>
</details>

---

<details>
	<summary>Does this application work for the latest beta version of iOS ?</summary>
	<span markdown="1">It might, but it is not officially supported. If you try to use it and a DeveloperDiskImage is downloaded, it might happen, that the DeveloperDiskImage is outdated by the time the next beta is released. This will lead to errors when uploading the DeveloperDiskImage or when trying to spoof the location. In this case you have to manually redownload the lastest DeveloperDiskImage. See ['Refresh DeveloperDiskImage files'](../order-3-preferences/topic-1-developerdiskimage.html) for more details.</span>
</details>

---

<details>
	<summary>Why is my device not detected via Wi-Fi ?</summary>
	<span markdown="1">Most likely your device is not setup correctly. See ['Detect devices in your network'](../order-3-preferences/topic-2-network.html) for more details.</span>
</details>

---

<details>
	<summary>Is my Apple Watch or my Apple TV supported ?</summary>
	<span markdown="1">All Apple TVs after the Apple TV third generation should work. All Apple Watches should work as well. The only problem is, that *LocationSimulator* does not provide download links for the DeveloperDiskImage for these platforms. If you manually add a DeveloperDiskImage for your iOS version and platform everything should work as expected. See ['Add DeveloperDiskImage files'](../order-3-preferences/topic-1-developerdiskimage.html) for more details. </span>
</details>

---

<details>
	<summary>I keep getting `Error changing location` ?</summary>
	<span markdown="1">If you are using iOS 16.0 or later make sure that you activated [Developer Mode](https://developer.apple.com/documentation/xcode/enabling-developer-mode-on-a-device). If this does not fix your problem, you most likely used the wrong *DeveloperDiskImage* or it got somehow corrupted. Note, that each time you change the *DeveloperDiskImage* in LocationSimulator you must reboot your iOS device. Otherwise the new *DeveloperDiskImage* ist not used. You can try the following solutions to fix corrupted *DeveloperDiskImages*.    
    
**A. First solution:**    
1. Turn off your iOS device completely (slide to power off)    
2. Open LocationSimulator    
3. Open `Preferences…` &rarr; `DiskImages` &rarr; `iPhoneOS`    
4. If your iOS version appears in the list, select the entry and click the `⟳` button, if not skip to 6    
5. A new download should now be initiated     
6. Turn on your iOS device    
7. Try to use LocationSimulator    
    
**B. Second solution:**    
1. Turn off your iOS device completely (slide to power off)    
2. Install the latest version of `Xcode.app` or `Xcode-beta.app`    
3. Open ```/Applications/Xcode.app/Contents/Developer/Platforms/iPhoneOS.platform/DeviceSupport/YOUR_IOS_VERSION/``` in Finder    
4. Open LocationSimulator    
5. Open `Preferences…` &rarr; `DiskImages` &rarr; `iPhoneOS`    
6. Click the `+` button and add the files you opened in finder. For `version` enter your iOS version, e.g. 16.0    
7. A a new entry with your iOS version appears in the list    
8. Turn on your iOS device    
9. Try to use LocationSimulator    
</span>
</details>

---


<details>
	<summary>Should I use this software to cheat in games?</summary>
	<span markdown="1">
You really shouldn't. Even if you don't care about the morals of cheating, this method is not safe for this use case !       
    
Since iOS 15 there is a direct API in `CLLocationSourceInformation` to detect if the location is simulated: `var isSimulatedBySoftware: Bool`. For earlier versions of iOS a fake location can be detected by the `CLLocation` property `speed`, which always returns -1 if the location is simulated or the `altitude` of 0.    
    
**Can you circumvent these limitations?**    

No I can't. This is a hard limitation by the API. If you want to fake the location without leaving any trace, you need to jailbreak your device. There is no other way.
    
    
**Can any other PC software simulate the location without leaving a trace?**    

As said bevor the answer is no. There is no API to change the location of an iOS device from a Mac or PC without the limitations mentioned above.
</span>
</details>

---