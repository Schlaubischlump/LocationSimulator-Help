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