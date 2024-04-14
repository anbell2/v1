# ESP32 Remote Display for Valentine One (Gen 2)

This is a remote display for the Valentine One Gen 2 radar detector written in C++, inspired by SquirrelMaster on [rdforum](http://rdforum.org)

Connectivity is via Bluetooth Low Energy (BLE) and currently has only been tested as a solo accessory. If you want to use this along
with another accessory or app such as JBV1, you will need a [V1Connection LE](https://store.valentine1.com/store/item.asp?i=20232). Again
this is untested and is something I'll be considering in a future release. A quick run-down of the radar-related features:
- Radar direction (front/side/rear)
- Band display (in GHz)
- Signal strength per alert
- Alert table support (up to 3 alerts)
- Priority alert will always be displayed

The hardware is a [LilyGO T-Display S3](https://www.lilygo.cc/products/t-display-s3?variant=42284559827125) which can easily be obtained for under
$15 for most US-based users. It is an ESP32 microcontroller with WiFi, Bluetooth Low-Energy (BLE), and a 1.9" TFT display. Physical connectivity is
via USB-C. I have not tested this on other boards but if there's interest, mail me a board or fork this repo.

Here's what's done in the current release:
- BLE auto-scan for connecting to a V1 Gen2 advertising the appropriate characteristics / service
- WiFi enabled (by default as an AP for user configuration), defaults as follows:
    - SSID: v1display
    - Password: password123
    - IP: 192.168.242.1
- Web-based UI for configuration and requesting device details (needs work)
- Portrait and Landscape modes
- "Store mode" for comparing portrait vs landscape (useful if modifying colors/layout)

Here's the TODO as of April 15, 2024: (in descending order of priority)
- Deeper integration between web front-end and ESP32 backend
- Dedicated Laser alerting
- Add OTA functionality
- Further code optimization and consolidation (a bit messy on initial push)
- Add graphics/screenshots into this README

If you have suggestions or requests, please ping me on the [rdforum valentine one](https://www.rdforum.org/threads/136559/) sub on rdforum.

# Installing to your T-Display-S3

1. Clone this repo
2. Load the project in VSCode (or your IDE of choice)
3. Compile and push to your board
4. Turn on your V1, then connect the board to a USB-C power source in your vehicle
