# NeuronBot2_LED (Arduino Nano for example)

This document shows that how to install Arduino IDE and how to flash new Arduino program into NeuronBot.

### Arduino IDE Installation

Search Arduino IDE on Ubuntu Software
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/aduino_search.png">

Install Arduino IDE on Ubuntu Software
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/arduino_install.png">

### Arduino IDE Initialization

When you first open Arduino IDE, you may see below warning:
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/usermod.png">

Please enter below command to give the permission to Arduino USB board, and then reboot your PC.

```bash
sudo usermod -a -G dialout ros
```

### Arduino IDE Library

Before programing and compiling the Arduino sketch, you have to install the required LED Library.

Please click **Manage Library** to open the Library Manager
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/arduino_manage_library.png">

Install **Adafruit NeoPixel** library for the Arduino Board.
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/download_adafruit.png">

### Arduino IDE Settings for Sketch Upload

Now configuring the Arduino IDE to correctly connect the Arduino board in the NeuronBot.

Set the **Board** to Arduino Nano
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/Nano_BoardSet.png"> 

Set the **Processor** to ATmega328P (Old Bootloader)
<img src="https://github.com/Adlink-ROS/NeuronBot_LED/blob/master/images/processorset.png"> 

Find the actual path of symbolic link /dev/neuronbotLED in Ubuntu terminal
<img src="https://github.com/Adlink-ROS/NeuronBot_LED/blob/master/images/neuronbotLED.png"> 

Set the **Port** of Arduino IDE to `/dev/ttyUSB0`
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/portset.png">

Open **Arduino_Nano.ino** in Arduino IDE
<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/arduino_open_sketch.png">

Click **Verify** button to verify the sketch

<img src="https://github.com/Adlink-ROS/NeuronBot2_LED/blob/master/images/verify.png">

Click **Upload** button to write the sketch into Arduino Nano

<img src="https://github.com/Adlink-ROS/NeuronBot_LED/blob/master/images/upload.png">

### Dependency installation on Ubuntu

Install the dependency
```sh
pip install pyserial   # if pip not found, use pip3 instead
```

### Check the function

Now you can verify your new Arduino program by executing the script:

```sh
python led_control.py --port /dev/neuronbotLED --mode 6
# port : the port where the USB cable is, e.g., /dev/neuronbotLED.
# mode : test built-in LED mode in this script
```
