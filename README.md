# Radin-security-camera
Security camera based on ESP32cam with modified sketch to set low framerate in order to solve the problem of enormous saved video stream files and added relay function for external projector (normal ligh or IR).

![alt text](https://github.com/BL08FR/Radin-security-camera/blob/main/fpsrelay.jpg?raw=true)

 ###### MODIFICATION TO SET MAX. FRAMERATE AND RELAY (by Blaise Lapierre 08/12/2022). ######
 Tested on HW-818 (AIthinker+CH340) with ov2640 camera.
 - Config like an AI thinker type: type of card->ESP32 arduino->AI thiner ESP32cam
 - For stream saving (ex: security cam) to avoid too big files, set a low framerate 1/2FPS.
 - Relay can be used to switch on projector (normal light or IR for nightvision).
  
 /!\ Check well all settings in myconfig.h tab!
 
 /!\ Don't use relay if you are using SD card!
 
 /!\ Pay attention to power supply before to accuse the code (what I did), 5V 1A phone charger is NOT enough, you may loose the stream time to time, use 2A.

You can use in pair with That project android app:
https://youtu.be/S6Y_n-Axtmk
https://play.google.com/store/apps/details?id=com.thatproject.esp32camviewer.android


Updates:

[15/12/22] Default FPS set to 1, webpage start in full controls mode.
Autorelay function update:
If ambient light level is lower than threshold -> switch ON projector via relay -> get the "new light value" with relay ON.
If ambient light become higher than threshold AND +10 from the "new light value" -> switch OFF projector via relay.

[16/12/22] 1 FPS didn't provide a stable stream on long term use, modified to 1.25 real FPS when set to 1 (value tested stable during 24hours).
