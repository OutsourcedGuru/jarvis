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

![c2-r2-header](https://user-images.githubusercontent.com/15971213/32683766-b7311db8-c632-11e7-9f81-8d5e35315461.jpg)

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

![overview](https://user-images.githubusercontent.com/15971213/38169467-911c15ea-351f-11e8-9355-9d65481cd527.png)

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
