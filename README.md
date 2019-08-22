# jarvis
An AI interface for controlling a 3D printer remotely via Amazon Alexa using a J.A.R.V.I.S. interface

[Related blog post](https://outsourcedguru.wordpress.com/2018/03/19/j-a-r-v-i-s-realized/)

![J.A.R.V.I.S.](https://outsourcedguru.files.wordpress.com/2017/08/jarvis.jpg?w=739)

## Amazon Alexa Intents
* Open: "Open Jarvis" => Introductory phrase
* StatusPrinterIntent: "Ask Jarvis for printer status" => "charming-pascal is ready and operational"
* ShutdownPrinterIntent: "Ask Jarvis to shut down the printer" => Exit phrase
* RebootPrinterIntent" "Ask Jarvis to reboot the printer" -> "The printer has been rebooted"
* RestartPrinterIntent: "Ask Jarvis to restart the printer" => "The printer service has been restarted" 
* StatusPrintIntent: "Ask Jarvis for job status" => "charming-pascal is currently printing RC_clip.gcode"
* StatusSelectionIntent: "Ask Jarvis which file is selected" => "RC_clip.gcode is currently selected"
* StartPrintIntent: "Ask Jarvis to start the print" => "The selected print job has been started"
* StopPrintIntent: "Ask Jarvis to cancel the job" => "The selected print job has been canceled"
* PausePrintIntent: "Ask Jarvis to pause the job" => "The selected print job has been paused"
* ResumePrintIntent: "Ask Jarvis to resume the print job" => "The selected print job has been resumed"
* ListFilesIntent: "Ask Jarvis to list the files" => "First: Vase, second: Birdhouse..."
* SelectFileIntent: "Ask Jarvis to select the third file" => "The third file, LAWN_GNOME, has been selected"
* StartWebcamIntent: "Ask Jarvis to start the webcam" => "The webcam service has been started"
* StopWebcamIntent: "Ask Jarvis to stop the webcam" => "The webcam service has been stopped"
* PreheatPLAIntent: "Ask Jarvis to preheat for PLA" => "The printer is preheating for PLA filament"
* PreheatABSIntent: "Ask Jarvis to preheat for ABS" => "The printer is preheating for ABS filament"
* PreheatCFPLAIntent: "Ask Jarvis to preheat for carbon fiber PLA" => "The printer is preheating for carbon fiber PLA filament"
* CoolExtruderIntent: "Ask Jarvis to cool the extruder" => "The printer is cooling down the extruder"
* CancelIntent: "Ask Jarvis to cancel" => etc
* HelpIntent: "Ask Jarvis for help" => etc
* StopIntent: "Ask Jarvis to stop" => etc

## Amazon Lambda Function
Each of the related intents above marries with a function within a Lambda function hosted at Amazon AWS.

## OctoPrint
Most of the actual functionality is provided via the wonderful [API](http://docs.octoprint.org/en/master/api/) within OctoPrint.

## Firewall Proxy
It was necessary to write and host a firewall proxy to allow the inbound Internet-based traffic to be proxied to/from the printer itself. I wrote this in Node.js and it's called `octo-proxy`. My firewall then forwards an emphemeral port to this **Raspberry Pi Zero W** computer which runs the proxy.

## Remote Power Management
Teaming this with a [TP-Link Smart Plug](https://www.tp-link.com/us/products/details/cat-5516_KP100.html), I am also able to power ON/OFF the entire printer itself remotely via the Amazon Alexa interface.

## Future Development
I intend to create a website which allows people to introduce their own 3D printers as a profile and then remotely-control them via an authenticated console. Obviously, each person would need their own proxy but I imagine generating and selling these as a low-cost add-on to the otherwise (assumed) free service.

I'll also need to proxy the printer's webcam service, to stop/start the webcam, etc. But the functionality at the moment is rather good so far.

|Donate||Cryptocurrency|
|:-----:|---|:--------:|
| ![eth-receive](https://user-images.githubusercontent.com/15971213/40564950-932d4d10-601f-11e8-90f0-459f8b32f01c.png) || ![btc-receive](https://user-images.githubusercontent.com/15971213/40564971-a2826002-601f-11e8-8d5e-eeb35ab53300.png) |
|Ethereum||Bitcoin|
