# Controlling a 3D Printer (Even Remotely) With Amazon Alexa and a Firewall Proxy

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

# J.A.R.V.I.S.

&nbsp;

The app is themed on the artificial intelligence (AI) character from the Iron Man movie series, as voiced by Paul Bettany. (You may recall the dialogs between the Tony Stark character and his computer.)

&nbsp;

![J.A.R.V.I.S.](https://outsourcedguru.files.wordpress.com/2017/08/jarvis.jpg?w=739)

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Developed code for this project:
* **octo-proxy** server running at home (250 lines of JavaScript) on a Raspberry Pi Zero W computer
* **J.A.R.V.I.S.** app in the Alexa Skills Kit cloud (ASK)
* **jarvisApp** Lambda cloud function at Amazon (over 1200 lines of JavaScript)

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Components
* Robo C2 printer
* Amazon Echo Dot
* Two Kasa-based TP-Link Smart Plugs to control power (printer & proxy)
* Netgear firewall

![img_0485](https://user-images.githubusercontent.com/15971213/38272991-b765cb66-373f-11e8-93fa-bbf141b112c5.png)
![img_0486](https://user-images.githubusercontent.com/15971213/38273068-df05fb78-373f-11e8-9657-27dff65155ad.png)
![img_0487](https://user-images.githubusercontent.com/15971213/38273095-f8474722-373f-11e8-85d3-1f15b549142f.png)
![img_0488](https://user-images.githubusercontent.com/15971213/38273124-090f55fe-3740-11e8-9dc5-0f473ec19c77.png)

&nbsp;

&nbsp;

&nbsp;

## Overview
1. A command is spoken into an **Amazon Echo Dot** device either at home or remotely
2. This gets directed to an **Amazon Skill** (ASK) in the cloud
3. An **intent** is determined and forwarded to an **Amazon Lambda** function (JavaScript)
4. An HTTP GET request is directed to my firewall's external IP address with an ephemeral port
5. The firewall at my home redirects the traffic to a server
6. A **Raspberry Pi Zero W** is running **octo-proxy** (JavaScript) to authenticate and proxy the traffic to my printer
7. My 3D printer then responds to the request and the information flows back up the chain

&nbsp;

![overview](https://user-images.githubusercontent.com/15971213/38169486-e1d25ab2-351f-11e8-9e00-cd97f4c292c6.png)

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Capabilities
1. Power ON/OFF both printer and the proxy server
2. Shutdown and reboot the Raspberry Pi inside the printer
3. Restart the OctoPrint service running inside the printer
4. Get either printer or print job status
5. List files on the printer and select one to print
6. Start, stop, pause and resume printing of a file
7. Preheat the extruder for three different filament types as well as cool it down again
8. Start and stop the webcam service
9. Open the J.A.R.V.I.S. app itself to hear a dialog event from the Iron Man movie

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

## Future Development

The next logical step is to create a website concept which allows others to remotely control their own printers.

&nbsp;

&nbsp;

&nbsp;

&nbsp;
