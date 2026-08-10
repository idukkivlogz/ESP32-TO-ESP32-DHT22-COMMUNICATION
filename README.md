# ESP32-TO-ESP32-DHT22-COMMUNICATION
Wireless Temperature &amp; Humidity Monitoring Using ESP32 and ESP-NOW  A wireless environmental monitoring project using two ESP32 boards, a DHT22 temperature &amp; humidity sensor, and an OLED display.  The first ESP32 reads temperature and humidity from the DHT22 sensor and transmits the data wirelessly to the second ESP32 using ESP-NOW. 
⚠️ One important step: MAC address

You need to tell ESP32 #1 where to send the data.

First upload the Receiver code to ESP32 #2.

Open:

Serial Monitor → 115200 baud

You'll see something like:

Receiver MAC Address: 24:6F:28:12:34:56
Receiver ready!

Copy that address.

For example:

24:6F:28:12:34:56

Change this part in the transmitter code:

uint8_t receiverMAC[] = {
  0x24, 0x6F, 0x28, 0x12, 0x34, 0x56
};

Then upload the transmitter code to ESP32 #1.

Your final OLED will look approximately like:
       DHT22 DATA
------------------------
T: 28.6 C

H: 64.3 %

And you can have the two ESP32 boards completely wireless—only the DHT22 is connected to ESP32 #1 and the OLED to ESP32 #2.

If your OLED is the 128×64 0.96" I2C type, these connections and code are ready to use.
