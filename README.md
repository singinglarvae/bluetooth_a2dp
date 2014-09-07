bluetooth_a2dp
==============

Bluetooth A2DP for Raspberry pi

The following should provide a direct audio connection over bluetooth (a2dp) for a Rasp

#Required:
- Raspbian (version 2014-06-20 was used)
- Packages: bluez pulseaudio-module-bluetooth python-gobject python-gobject-2

#Instruction:
1. Install the required packages: sudo apt-get install bluez pulseaudio-module-bluetooth python-gobject python-gobject-2
2. Edit the audio.conf file: sudo nano /etc/bluetooth/audio.conf
3. Add the following line after [General]: (Enable=Source,Sink,Media,Socket)
4. (nb: you may edit other option within this directory such as bluetooth name and so on)
5. Make sure to enable bluetooth at startup: sudo systemctl enable bluetooth.service
6. Make sure to enable the sound driver at startup: sudo echo "snd-bcm2835" >> /etc/modules-load.d/snd-bcm2835.conf 
7. Reboot: sudo reboot
8. As root, move the various files to their required location
 *If needed, change the configuration within the files*
9. Allow execution for all files: sudo chmod +x
10. Reload the udev rules: sudo udevadm control --reload-rules
11. Start the bluetooth_a2dp service: sudo service bluetooth_a2dp start
All done!

#Inspired by:
- http://www.instructables.com/id/Turn-your-Raspberry-Pi-into-a-Portable-Bluetooth-A/?ALLSTEPS
- http://kmonkey711.blogspot.co.uk/2012/12/a2dp-audio-on-raspberry-pi.html
- http://blog.mrverrall.co.uk/2013/01/raspberry-pi-a2dp-bluetooth-audio.html
