bluetooth_a2dp
==============

Bluetooth A2DP for Raspberry pi

The following should provide a direct audio connection over bluetooth (a2dp) for a Rasp

Required:
- Raspbian (version 2014-06-20 was used)
- Packages: bluez pulseaudio-module-bluetooth python-gobject python-gobject-2

Instruction:
- Install the required packages: sudo apt-get install bluez pulseaudio-module-bluetooth python-gobject python-gobject-2
- Edit the audio.conf file: sudo nano /etc/bluetooth/audio.conf)
- Add the following line after [General]: (Enable=Source,Sink,Media,Socket)
- Make sure to enable bluetooth at startup: sudo systemctl enable bluetooth.service
- Make sure to enable the sound driver at startup: sudo echo "snd-bcm2835" >> /etc/modules-load.d/snd-bcm2835.conf 
- Reboot: sudo reboot
- As root, move the files to the required location
- If required, change the configuration within the files
- Allow execution: sudo chmod +x
- Reload the udev rules: sudo udevadm control --reload-rules
- Start the bluetooth_a2dp service: sudo service bluetooth_a2dp start
All done!

Inspired by:
- http://www.instructables.com/id/Turn-your-Raspberry-Pi-into-a-Portable-Bluetooth-A/?ALLSTEPS
- http://kmonkey711.blogspot.co.uk/2012/12/a2dp-audio-on-raspberry-pi.html
- http://blog.mrverrall.co.uk/2013/01/raspberry-pi-a2dp-bluetooth-audio.html
