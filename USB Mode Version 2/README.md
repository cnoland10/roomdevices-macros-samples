# USB Mode Version 2 🎉

![USB Mode Home Screen](images/UsbMode_Home.png)

## About

The USB Mode macro is a community driven solution that enables USB Passthrough for Cisco Room devices that do not natively support this feature.

USB Passthrough is a feature, found on products like the Webex Room Kit Mini and the Webex Desk Pro, that allows you to take advantage the device's rich microphone(s), intelligent camera(s) and powerful speaker(s) as a sophisticated webcamera for various 3rd party software clients.

To better illustrate how this macro works, please click on the video demo below to see USB mode in action

[![USB Mode Video Demo](https://img.youtube.com/vi/fFKpSABTkDQ/0.jpg)](https://www.youtube.com/watch?v=fFKpSABTkDQ)

## Before you begin
USB Mode is only 1 flavor of the USB Passthrough solution. Many new Room Devices support this natively and we recommend you work with the native tools built into the product if available.

Check out the [USB Mode Endpoint Compatibility Matrix](#usb-mode-endpoint-compatibility-matrix) below to see which USB solution is right for you.

## How does the script work
While USB mode is enabled, your Room Device's base configuration is stored in memory and then reconfigured to send Microphone Data out the Line Output of your device and your Main Source video out the last video output connection(Model Dependent); these feeds are fed into a compatible USB capture card(See docs for details). 

The room devices native UI elements, such as calling, sharing, meetings etc, are hidden, your presentation is started and the device is placed into an infinite Do Not Disturb(DND) Loop.

These elements are hidden and DND is enabled to prevent calling out or in while USB mode is enabled in order to prevent confusing the user as to what the system is doing.

![USB Mode Home Screen](images/UsbMode_Enabled.png)

When USB mode is Disabled, your system will show all Native UI Elements, disengage infinite DND and recover your system's base configuration for full Webex and SIP use.

## Requirements
- A copy of the [Deployment Guide](https://github.com/CiscoDevNet/roomdevices-macros-samples/raw/master/USB%20Mode%20Version%202/USB%20Mode%20V2%20Guides.zip)
- A [compatible Room Device](#usb-mode-endpoint-compatibility-matrix) either on
  - Latest stable software channel
  - Non-deferred software release
- Admin Privileges to your Room Device
- Ability to navigate the Macro Editor
- Compatible USB Capture Device
- Knowledgable on AV design and Implementation

## How to get started
- Download a copy of the [Deployment Guide](https://github.com/CiscoDevNet/roomdevices-macros-samples/raw/master/USB%20Mode%20Version%202/USB%20Mode%20V2%20Guides.zip), which contains all the files you need, and follow the instructions in the guide

## Macro Deployment Tools
- Use the [RoomOs](https://roomos.cisco.com/macros) website to connect to your device and install the script with installer tool
- For bulk deployment, Ce-Deploy has you covered
  - [Ce-Deploy Community Space](https://eurl.io/#SJWfk6qUV)
  - [Ce-Deploy Builds](https://github.com/voipnorm/CE-Deploy/releases/)

## More Useful Links
### Join the Community!
The [PROJECT: USB Mode](https://eurl.io/#L6Rcn39Rn) space on Webex is filled with over 1500 partners, integrators, customers and USB enthusiasts; all sharing their experience, creativity and use cases all around USB Mode. Definitely a great place to ask questions.

### Blog Posts
  - [Innovations from Webex Experts](https://blog.webex.com/webex-devices/innovations-from-webex-experts-making-devices-even-better/)
  - [USB Passthrough Mode on Video Endpoints](https://gblogs.cisco.com/ch-tech/usb-passthrough-mode-on-video-endpoints/)
  - [Unlocking BYOM in a Webex Environment](https://community.cisco.com/t5/announcements/walkthrough-wednesday-unlocking-byom-in-a-webex-environment/m-p/4549307#M850)

### Videos

| USB- Passthrough with Cisco Video Devices | Turn Cisco Video Endpoint into USB Camera |
| ------------------ | ---------- |
| [<img src="https://img.youtube.com/vi/R5Hde9Zvbvw/0.jpg" width="400">](https://www.youtube.com/watch?v=R5Hde9Zvbvw) | [<img src="https://img.youtube.com/vi/ta4OZ0_wbVQ/0.jpg" width="400">](https://www.youtube.com/watch?v=ta4OZ0_wbVQ) |
|USB Mode 2 - Configuration||
|[<img src="https://cdn-3-d.app.vidcast.io/f4/0b/05/f40b0539-d9fe-478b-9164-da52bc868d93/thumbnail_screen_1645822157211.jpeg?Expires=1645829397&amp;Signature=H0tbr2uCkaP3-idv~OZEsS2Gx0jNpNEpiv4KazXQ2zJ1nG9yS28zCUYo3MQ63Fe3FhPMmSbn2EPSJ0qquT13L2gFzP-nZvAR-v7XPdFEhwsjClO-qdY5hiIWq6xPuoCw5b3YJOSOS0sLzXo6sHH70a8akZhqzc1SvkYONH-4I7H-~ZEO9UsBHIHqz3hJ15ST2kFEGL4QGpSksWql6ewHshVEvOcFmFFncJL-fZP5tm6Iv8EdXRyIL0-lFo1UUA4VklNK29prkH2765YbIwky2lQCbo3vLJzwo3QFpXsO3zqS0peWg6dT3~S7RjwkjxG7eiXC1zOomFIRCBg22ZTtPA__&amp;Key-Pair-Id=K7MMR7AZ73QPM" width="400">](https://app.vidcast.io/share/67079b20-5fa7-4fbb-80ba-099d485728b3)||

## Author(s)

|                  | **Enrico Conedera**                 | **John Yost**                | **Robert(Bobby) McGonigle**  |
|------------------|-------------------------------------|------------------------------|------------------------------|
| **Contribution** | Project Lead                        | Consulting Engineer          | Macro Author                 |
| **Title**        | Senior Technical Marketing Engineer | Technical Marketing Engineer | Technical Marketing Engineer |
| **Org**          | Cisco Systems                       | Cisco Systems                | Cisco Systems                |
| **Contact**      | econeder@cisco.com                  | johyost@cisco.com            | bomcgoni@cisco.com           |

## Acknowledgments
- Zacharie Gignac from Université Laval in Canada
  - His contributions to the memory storage functionality are invaluable
- All of our community members in the Project USB space on Webex
  - You're all awesome, thank you for your ideas, patience and testing 😃

## FAQ
### Will Cisco TAC give me assistance?
- TAC does not support Macros, thus the USB mode macro won't be supported. Any hardware and software support you have with Cisco will still be covered, but they may require you to disable USB while you troubleshoot with them.
### Why is selfview full screen on one of my displays?
- USB Mode relies on your selfview feed being sent to the USB Capture Device
- If using a Loop Through capture card like the Inogeni 4KX-Plus, then you'll see a full selfview on your second display while USB mode is in use
### Where can I get assistance?
- USB mode is a community driven solution. We recommend you read the all the documentation in the [Deployment Guide](https://github.com/CiscoDevNet/roomdevices-macros-samples/raw/master/USB%20Mode%20Version%202/USB%20Mode%20V2%20Guides.zip).
- If you still need more assistance, join the [PROJECT: USB Mode](https://eurl.io/#L6Rcn39Rn) space on Webex
### Can I hide selfview on the second display?
- This would require additional design and hardware outside this scope. Ask your AV integrator on possible solutions
### USB stops working and I get an error message?
- When USB mode detects no Video Input signal from a computer, it's designed to disengage USB mode. An active presentation is required for USB mode to work, so be sure to share your screen before activating USB mode
### Why do I see my presentation source as my USB camera feed?
- Enable USB Mode must be pressed for the camera view to become available
- If you still don't see your camera, disable USB mode and restart your codec
### Why can't people on my call hear my Audio?
- USB Mode requires an audio connection be made to the USB Capture card
- Check the wiring guide in the deployment guide
- Keep in mind, not all USB capture cards are the same, some may require a special attenuation cable for audio to function properly

## USB Mode Endpoint Compatibility Matrix
### Key
- Native USB: Devices that have USB Passthrough built into their hardware. No need for a macro and highly recommended 😃
- Native Inogeni: Native OS support for USB mode, no macro required. Inogeni 4KX-Plus Capture device required. (Not currently available)
- Macro 1-3: Original USB Mode Macro, accessible in the USB Mode community space. Recommend upgrading to USB Mode Version 2 when possible.
- Macro 2-2-10: USB Mode Version 2


| CODEC              | Native USB | Macro 1-3 | Macro    2-2-10 | Native USB Inogeni  |
| ------------------ | ---------- | --------- | --------------- | ------------------- |
| C-Series and older | **No**     | **No**    | **No**          | **No**              |
| Mx200/300 G1       | **No**     | **No**    | **No**          | **No**              |
| Mx200/300 G2       | **No**     | **No\***  | **No**          | **No**              |
| Dx70/Dx80          | **No**     | **No**    | **No**          | **No**              |
| Sx10               | **No**     | **No**    | **No**          | **No**              |
| Sx20               | **No**     | **No\***  | **No**          | **No**              |
| Sx80               | **No**     | **Yes**   | **Yes**         | **No**              |
| Mx700/700ST        | **No**     | **Yes**   | **Yes**         | **No**              |
| Mx800/800ST/800D   | **No**     | **Yes**   | **Yes**         | **No**              |
| Board 55/55s       | **No**     | **No**    | **No**          | **No**              |
| Board 70/70s       | **No**     | **No**    | **No**          | **No**              |
| Board 85s          | **No**     | **No**    | **No**          | **No**              |
| Room USB           | **Yes**    | **No**    | **No**          | **No**              |
| Room Kit Mini      | **Yes**    | **No**    | **No**          | **No**              |
| Room Kit           | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| CODEC Plus         | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| CODEC Pro          | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| Room 55/55D        | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| Room 70D/70S       | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| Room 70D/70S G2    | **No**     | **Yes**   | **Yes**         | **FR (Room OS 11)** |
| Room 70 Panorama   | **No**     | **No**    | **FR (2-3-0)**  | **FR (Room OS 11)** |
| Room Panorama      | **No**     | **No**    | **FR (2-3-0)**  | **FR (Room OS 11)** |
| Desk Mini          | **Yes**    | **No**    | **No**          | **No**              |
| Desk               | **Yes**    | **No**    | **No**          | **No**              |
| Desk Hub           | **Yes**    | **No**    | **No**          | **No**              |
| Desk Pro           | **Yes**    | **No**    | **No**          | **No**              |
| Board Pro 55       | **Yes**    | **No**    | **No**          | **No**              |
| Board Pro 75       | **Yes**    | **No**    | **No**          | **No**              |

\* => USB mode script will function, but this endpoint requires a 3rd party audio solution to be fed into the USB Capture Device<br />
FR => Future Release, Tentative release version within parenthesis