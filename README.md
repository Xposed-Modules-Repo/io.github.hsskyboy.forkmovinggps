<div align="center">

# Fork Moving GPS

[![Stars](https://img.shields.io/github/stars/HSSkyBoy/Fork-Moving-GPS?style=flat-square)](https://github.com/HSSkyBoy/Fork-Moving-GPS/stargazers)
[![Downloads](https://img.shields.io/github/downloads/HSSkyBoy/Fork-Moving-GPS/total?label=Downloads&logo=GitHub&style=flat-square)](https://github.com/HSSkyBoy/Fork-Moving-GPS/releases)
[![Release](https://img.shields.io/github/v/release/HSSkyBoy/Fork-Moving-GPS?style=flat-square)](https://github.com/HSSkyBoy/Fork-Moving-GPS/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/HSSkyBoy/Fork-Moving-GPS/apk.yml?style=flat-square)](https://github.com/HSSkyBoy/Fork-Moving-GPS/actions/workflows/apk.yml)
[![License](https://img.shields.io/github/license/HSSkyBoy/Fork-Moving-GPS?style=flat-square)](https://github.com/HSSkyBoy/Fork-Moving-GPS/blob/master/LICENSE)

<p>
    A powerful GPS setter based on the Xposed framework.<br>
    This fork is designed to provide full support for <b>Android 15+</b> (up to Android 16 Beta).
</p>

<a href="https://github.com/HSSkyBoy/Fork-Moving-GPS/releases">
    <img src="https://raw.githubusercontent.com/NeoApplications/Neo-Backup/refs/heads/main/badge_github.png" alt="Get it on GitHub" height="80">
</a>

</div>

## Requirements

*   **Android OS:** Android 8.1 - Android 16 Beta 2
*   **Rooted:** Xposed Framework (LSPosed, etc.)
*   **Non-Rooted:** Supported via LSPatch (requires manually embedding the module)
*   **Dependencies:** Google Play Services (GMS) is required for Maps and Location services.

## Key Features

### 🚀 Route & Movement Simulation
-   **Realistic Moving Simulation:** Simulate GPS movement along routes with adjustable speeds (1-120 km/h).
-   **Advanced Route Planning:** Plan complex routes with multiple waypoints and follow them automatically.
-   **Playback Controls:** Pause, resume, and stop navigation with real-time progress tracking.
-   **Trip Data:** Monitor traveled distance and remaining route time in real-time.

### 🕹️ Controls & Interaction
-   **Smart Joystick:** Adjust location on the fly with an overlay joystick. Movements follow screen orientation, not compass direction.
-   **Quick Actions:** Instantly replace location without unsetting/resetting.
-   **Drag & Drop:** Long-press and drag the destination marker in search mode for precise positioning.
-   **Background Updates:** Real-time GPS position updates even when the app is in the background.

### 🛠️ Core Functionality
-   **System Integration:** Supports system server location APIs introduced in Android 14+.
-   **Privacy Focused:** Hook the app itself or the system server to bypass detection.
-   **Randomization:** Allows using a live updating random location in the vicinity of the set point.
-   **Modern UI:** Compatible with the latest Material Design standards.

## Demo

<div align="center">
    <video src="https://github.com/user-attachments/assets/388ac05c-db56-42ce-9253-2f1855800a5c" width="200" style="max-width: 100%;"></video>
</div>

## Motivation

An increasing number of apps are abusing the location permission for tracking purposes, preventing the user from using the app without granting the permission. Traditionally on Android, modifying the response from the android server is done using the mock location provider - however, the availability of this feature is device dependent. Additionally, some apps have started explicitly checking for signals regarding whether the location provided is reliable.

This module aims to mitigate this by providing an ability to either:
1.  Hook the app itself to modify the location it receives.
2.  Hook the system server if the app explicitly checks for whether itself is being hooked.

Specifically, it intercepts `android.location.Location` and `android.location.LocationManager` methods including:
-   [`getLatitude()`](https://developer.android.com/reference/android/location/Location#getLatitude())
-   [`getLongitude()`](https://developer.android.com/reference/android/location/Location#getLongitude())
-   [`getAccuracy()`](https://developer.android.com/reference/android/location/Location#getAccuracy())
-   [`getLastKnownLocation(String)`](https://developer.android.com/reference/android/location/LocationManager#getLastKnownLocation(java.lang.String))

## Credits

-   [Android1500](https://github.com/Android1500/GpsSetter) for the original GpsSetter targeting Android 8.1 to 13.
-   [MapLibre](https://github.com/maplibre/maplibre-native) & [microG](https://github.com/microg/GmsCore) for the underlying mapping and location technologies used in the development of this fork.
