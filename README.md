# Video #269 - Elecrow 3.5" TFT with ESP32 (built-in)

![Thumbnail-00028 (Custom)](https://github.com/RalphBacon/269-Elecrow-3.5-TFT-with-ESP32-built-in/assets/20911308/9e60afce-a3e3-4ff3-9346-b08cf9185151)  
### Video link: https://youtu.be/EMpF5-0YeSM 
<br>  

[![Flex PCBs Special Offer](https://user-images.githubusercontent.com/20911308/226928395-0f7add24-e5ca-4b13-a819-d330ae9f5f77.gif "PCBWay - up to 60% off Flex/Rigid PCBs")](https://pcbway.com/)  

### Intro  
Elecrow kindly asked me to review their combo ESP32/TFT screen board - rather similar to the one I used in my ESP32 Web Radio project a few years back (and which is still going strong!)  
https://www.elecrow.com/display/esp-hmi-display.html?idd=3  

I chose the 3.5" touch screen because it seemed the "best fit" for hobbyists, although I was tempted by the huge 7" screen they have too!  
https://www.elecrow.com/esp32-display-3-5-inch-hmi-display-spi-tft-lcd-touch-screen.html?idd=3  
At the time of writing (July 2023) it's on special offer. I recommend you also get the case, it's less than $2.  

### Libraries
Although Elecrow make a big splash on their website about using the open source LVGL (Light & Versatile Graphics Library), which I'm sure is great, I never got a chance to use it, as all the example sketches did not seem aimed at the ESP32 processor (example: the backlight control was attached to "pin 46" which the ESP32 doesn't even have). This will need more investigation.  
https://lvgl.io/  

Thankfully they also supplied a number of sketches that used the TFT_eSPI library, with which I'm quite familiar as I used it in the aforementioned ESP32 Web Radio project. It supports a huge number of TFT screen drivers; you just have to be sure you have uncommented out the line for your particular screen.  
https://github.com/Bodmer/TFT_eSPI  

### GPIO connections
The Elecrow ESP32 board uses the following GPIO pins for their TFT screen (important for any libraries) in the TFT_eSPI "User_Setup.h" file:
```
#define ILI9488_DRIVER

// Screen backlight control GPIO and what makes it turn on?
#define TFT_BL   27 
#define TFT_BACKLIGHT_ON HIGH

// Super important GPIO pin allocation for SPI
#define TFT_MISO 12
#define TFT_MOSI 13
#define TFT_SCLK 14
#define TFT_CS    15
#define TFT_DC    2 
#define TFT_RST   -1
#define TOUCH_CS 33

Also, as the SPI bus can run at various frequencies, they suggest to use these values:

#define SPI_FREQUENCY  27000000
#define SPI_TOUCH_FREQUENCY  2500000
#define SPI_READ_FREQUENCY  16000000
```
Once I'd got this information (it took a while) everything just fell into place and all was well.

I've also corrected one of their sketches that uses the ESP32's inbuilt DAC (Digital to Analog Conversion) that can read an .mp3 file and send the resulting audio to one of the DAC pins (either 25 or 26, in this case pin 26).

Just have a look at the folder and files attached to this GitHub to get yourself up and running in no time.

► List of all my videos
(Special thanks to Michael Kurt Vogel for compiling this)  
http://bit.ly/YouTubeVideoList-RalphBacon  

► Want to get an introductory discount from PCBWay? Follow this link:  
https://pcbway.com/g/SaH9tF  

► If you like this video please give it a thumbs up, share it and if you're not already subscribed please consider doing so and joining me on my Arduinite (and other μControllers) journey

My channel, GitHub and blog are here:  
\------------------------------------------------------------------  
• https://www.youtube.com/RalphBacon  
• https://ralphbacon.blog  
• https://github.com/RalphBacon  
• https://buymeacoffee.com/ralphbacon  
\------------------------------------------------------------------

My ABOUT page with email address: https://www.youtube.com/c/RalphBacon/about

