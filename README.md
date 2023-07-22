# Video #269 - Elecrow 3.5" TFT with ESP32 (built-in)

![Thumbnail-00028 (Custom)](https://github.com/RalphBacon/269-Elecrow-3.5-TFT-with-ESP32-built-in/assets/20911308/9e60afce-a3e3-4ff3-9346-b08cf9185151)  
### Video link: https://youtu.be/EMpF5-0YeSM 
<br>  

[![Flex PCBs Special Offer](https://user-images.githubusercontent.com/20911308/226928395-0f7add24-e5ca-4b13-a819-d330ae9f5f77.gif "PCBWay - up to 60% off Flex/Rigid PCBs")](https://pcbway.com/)  

### Intro  
Elecrow kindly asked me to review their combo ESP32/TFT screen board - rather similar to the one I used in my ESP32 Web Radio project a few years back (and which is still going strong!)

I chose the 3.5" touch screen because it seemed the "best fit" for hobbyists, although I was tempted by the huge 7" screen they have too! 

### Libraries
Although Elecrow make a big splash on their website about using the open source LVGL (Light & Versatile Graphics Library), which I'm sure is great, I never got a chance to use it, as all the example sketches did not seem aimed at the ESP32 processor (example: the backlight control was attached to "pin 46" which the ESP32 doesn't even have). This will need more investigation.

Thankfully they also supplied a number of sketches that used the TFT_eSPI library, with which I'm quite familiar as I used it in the aforementioned ESP32 Web Radio project. It supports a huge number of TFT screen drivers; you just have to be sure you have uncommented out the line for your particular screen.

### GPIO connections
The Elecrow ESP32 board uses the following GPIO pins for their TFT screen (important for any libraries):

