# Added build with OLED and Battery using the SSD1306 OLED and the TP4056 Charge Module

# DeauthDetector
Detect deauthentication frames using an ESP8266

![esp8266 deauth detector custom build](https://raw.githubusercontent.com/spacehuhn/DeauthDetector/master/images/device.jpg)

## Buy

[Maltronics](https://maltronics.com/) is selling a Deauth Detector based on this project:  

🛒 https://maltronics.com/products/deauth-detector

## Support us

Hey, do you like this kind of project?  

To make sure we can keep working on free and open-source projects like this,  
**please consider becoming a [:heart: Sponsor](https://github.com/sponsors/spacehuhntech) or support us via [:coffee: Ko-fi](https://ko-fi.com/spacehuhn).**  

Visit [spacehuhn.com](https://spacehuhn.com) to learn more about us. :chicken:

<a href='https://ko-fi.com/G2G75FA4V' target='_blank'><img height='36' style='border:0px;height:36px;' src='https://cdn.ko-fi.com/cdn/kofi2.png?v=3' border='0' alt='Buy Me a Coffee at ko-fi.com' /></a>

## How it works  

If the ESP8266 detects [deauthentication or disassociation frames](https://mrncciew.com/2014/10/11/802-11-mgmt-deauth-disassociation-frames/) it will turn on its LED. That's all ¯\ (ツ)/¯.  

![blinky esp8266 deauth detector](https://raw.githubusercontent.com/spacehuhn/DeauthDetector/master/images/blink.jpg)

So this is a good and cheap way to detect a [Wi-Fi deauthentication attack](https://en.wikipedia.org/wiki/Wi-Fi_deauthentication_attack).  

## How to install it  

**You will only need to follow one of the installation methods!**

### Uploading the .bin file

Upload the `deauth_detector.bin` using the [nodemcu-flasher](https://github.com/nodemcu/nodemcu-flasher) or the [esptool](https://github.com/espressif/esptool) from Espressif.

### Using Arduino

**1** Install [Arduino](https://www.arduino.cc/en/Main/Software)  
**2** Install the [ESP8266 SDK](https://github.com/esp8266/Arduino)  
**3** Download this project and open it with Arduino
**4** Maybe customize the code:
```
#define channel 1 //the channel it should scan on (1-14)
#define channelHopping true //scan on all channels
#define maxChannel 13 //US = 11, EU = 13, Japan = 14
#define ledPin 2 //led pin ( 2 = built-in LED)
#define inverted true // invert HIGH/LOW for the LED
#define packetRate 3 //min. packets before it gets recognized as an attack

#define scanTime 500 //scan time per channel in ms
```
**5** Upload the code to your ESP8266 (don't forget to set it to the right upload settings!)

**Done**
