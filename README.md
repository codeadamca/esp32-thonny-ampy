# esp32-thonny-ampy

A walkthrough of using Thonny and Ampy to connect to an ESP32 board for the first time. 

## ESP32 Drivers

Download the [ESP32 Drivers]() and walk through the installation process. Connect your ESP32 board using a USB cable. 

You will need to know the port name your board is connected to. Run the following command:

```
ls /dev/tty.*
```

The command will list your existing ports:

```
/dev/tty.Bluetooth-Incoming-Port	/dev/tty.SoundcoreLifeQ35-Spp1
/dev/tty.LEGOHubA8E2C19B5757-Ser	/dev/tty.usbserial-14220
/dev/tty.SoundcoreLifeQ35-OTA1
```

If possible, determine which port is your ESP32 board and copy it for later. 

If you are not sure which one is your board, disconnect your board, then run the list command again. Take note as to which port has been removed from the list. This is the port we will need for later. Mine port is:

```
/dev/tty.usbserial-14220
```

## LED

If your ESP32 board has an onboard LED, you can use pin two. If not, you will need to connect the circuit below and change the pin to 22:

![https://github.com/codeadamca/esp32-thonny-ampy/blob/main/esp32-led.png?raw=true]

## Thonny

Connect your board if it ois not connected. The follow these steps:

1. Download the [Thonny](https://thonny.org/) IDE
2. Create a new program and add the following code:

```python
import time
from machine import Pin

led = Pin(2, Pin.OUT)

while True:

    led.value(1)
    time.sleep(1)

    led.value(0)
    time.sleep(1)

    print.write("Working...")
```



## Tutorial Requirements:

* [Visual Studio Code](https://code.visualstudio.com/) or [Brackets](http://brackets.io/) (or any code editor)
* [Silabs ESP32 Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
* [Thonny](https://thonny.org/)
* [Ampy](https://pypi.org/project/adafruit-ampy/)
* [LMS-ESP32](https://antonsmindstorms.com/product/wifi-python-esp32-board-for-mindstorms/)

<a href="https://codeadam.ca">
<img src="https://codeadam.ca/images/code-block.png" width="100">
</a>
