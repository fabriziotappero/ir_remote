# Camera Infrared Remote Control
This repository contains the hardware and software implementation of a infrared 
remote control based on the [Espressif ESP32 module]. This module allow to remotely
control any infrared camera like, in my case, the Sony NEX6 camera.

<p align="center">
  <img src="https://github.com/fabriziotappero/ir_remote/blob/master/ir_camera_remote.jpg?raw=true" alt="Sublime's custom image"/>
</p>

Notice how an IR LED reader (U3) can be used to program the ESP32 so that the same
remote can actually control any camera. 

The schematic and PCB was designed using de EDA tool [KiCad] and all C++ 
code was compiled using the [Espressif ESP32 toolchain].

## Electronic Schematic
![][ir_remote_sch]

[ir_remote_sch]: https://github.com/fabriziotappero/ir_remote/blob/master/PCB/ir_remote_sch.png ""
[Espressif ESP32 module]: https://www.espressif.com/en/products/hardware/development-boards
[Espressif ESP32 toolchain]: https://dl.espressif.com/doc/esp-idf/latest/index.html
[KiCad]: http://kicad-pcb.org/

## Printed Circuit Board
This is the 2 layer PCB designed to sit on top of a ESP32 evaluation board.

![][ir_remote_pcb]

[ir_remote_pcb]: https://github.com/fabriziotappero/ir_remote/blob/master/PCB/ir_remote_pcb.png ""


## Hardware And Software Tools

Install **Kicad 5** on Debial-like Linux systems:
```
sudo add-apt-repository --yes ppa:js-reynaud/kicad-5
sudo apt-get update
sudo apt-get install kicad kicad-libraries
```

Install **ESP32 Espressif** compiler with its dependencies:
```
sudo apt-get install git wget make libncurses-dev flex bison gperf python python-serial

wget https://dl.espressif.com/dl/xtensa-esp32-elf-linux64-1.22.0-80-g6c4433a-5.2.0.tar.gz

tar -xvf xtensa-esp32-elf-linux64-1.22.0-80-g6c4433a-5.2.0.tar.gz
sudo mv xtensa-esp32-elf /opt
export PATH=/opt/xtensa-esp32-elf/bin:$PATH
```
Install the **ESP32 Espressif** developing environment IDF:
```
mkdir /opt/eps32 
cd /opt/eps32
git clone --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
git submodule update --init
export IDF_PATH=/opt/esp32/esp-idf
```

Begin from a simple example:
```
git clone https://github.com/espressif/esp-idf-template.git myapp
cd myapp
make menuconfig
make flash
```
A lot of code examples in ```/opt/esp32/esp-idf/examples```. For more information refer to the [Espressif ESP32 Programming Guide]

[Espressif ESP32 Programming Guide]: https://dl.espressif.com/doc/esp-idf/latest/index.html

## References

[Espressif ESP32 Programming Guide](https://dl.espressif.com/doc/esp-idf/latest/index.html)


## More Information
For any enquiry contact:

fabrizio.tappero@gmail.com
