# Rssi Beacon Collection
## Introduction
Proximity beacons provides us multiple helpful properties through bluetooth waves <br><br> <img src="https://user-images.githubusercontent.com/26139791/55882240-6062f780-5bce-11e9-9f51-9f8e952c214f.png"> <br><br>
Thanks to these values above, Bluetooth Low Energy(BLE) can calculate real time distance measurement from devices to Beacons which connected to them. Unfortunately, the bluetooth waves is not stable all time due to quality of obstacles which Bluetooth waves go through them. Obstacles may be walls, furnitures, water,... and others objects which cause signal attenuation, absorption or reflection.<br><br>
To make it clear, based on Fingerprint Statistic Wifi, Rssi Beacon Collection( helps us to collect RSSI value from Proximity Beacons for statistic strategy. By the way, sample collection would to be the next step to Weighted K-Nearest Neighbors or else algorithem to recogise the position of devices.
## Install
- Method 1: Clone the project and build it on your device by Android Studio.
- Method 2: Download [here](<!-- https://mega.nz/#F!5uYSiSbC!-lGSYnpysRhikIpfMDgemA -->) and install it by "Unknown sources" way.
## Database Diagram
![ERDDiagram](https://user-images.githubusercontent.com/26139791/55907900-3aefe100-5c02-11e9-98ed-1c0361d11ddd.jpg)
## Features
1. Create and manipulate **floors**
2. Create and manipulate **sample positions** at these **floors**.
3. Create and manipulate **samples** at each **sample positions**.
4. Service iBeacon scans beacons around device.
5. Collect **RSSI value** of beacons and store them to **Database**.
6. Export Database to file stored in *home/RSSIBeaconCollection/RSSIBeaconCollection.sqlite*
7. Setting term contains manipulation beacons and time scanning.
## Demo
<p align="center">
<img src="https://user-images.githubusercontent.com/26139791/55923507-0bf06400-5c30-11e9-9508-5287384929d5.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923602-5c67c180-5c30-11e9-803b-e3fb4079f60a.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923607-5e318500-5c30-11e9-8d29-1cadefc9620e.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923628-70132800-5c30-11e9-8c00-e46235cb6869.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923631-72758200-5c30-11e9-94c4-8a7078f64055.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923637-75707280-5c30-11e9-8e76-56cd299981b1.gif">
<img src="https://user-images.githubusercontent.com/26139791/55923641-773a3600-5c30-11e9-8877-20e0f779dded.gif">
</p>

## Interaction with Database
Use DB Browser for SQLite to manipulate Database of Collection<br>
<p align="center">
<img  width="400px" src="https://user-images.githubusercontent.com/26139791/55898748-7633e500-5bed-11e9-8a67-68758a5aa98b.png">
<img  width="400px" src="https://user-images.githubusercontent.com/26139791/55898790-92d01d00-5bed-11e9-86f9-a1cbd897bc39.png">
</p>

## Development Environment
- Compatible with Android 5.0 and above
- The App writen by Kotlin
- Tools in use:
  - Android Studio 3.3.2
  - DB Browser for SQLite
## External Libraries and Frameworks
- [Ankor Sqlite](https://github.com/Kotlin/anko/wiki/Anko-SQLite)
- [Toasty](https://github.com/GrenderG/Toasty)
- [iBeacon](https://estimote.github.io/Android-Proximity-SDK/)
## Author
- Khanh Huynh - Analyst, Design Architect, Developer- Junior at Software Engineering, University of Science, HCM, Vietnam
## Acknowledgements
- Thanks iBeacon for providing helpful technology.
- Thanks Estimote Beacon for wonderful documentations.
- Thanks [trackgovn.com](trackgovn.com) help me in contacting and buying beacons for testing and development process.

