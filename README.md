# ECG-DAQ

<p align="justify">

ECG-DAQ is the data acquisition system for electrocardiogram signals. This project is built from scratch meaning that all that schematics and PCB is made by myself based on the reference designs, simulations and laboratory testing on prototypes. 

PCB is logically/phisically divided into two parts - precision analog section where input signals, coming from the electrodes (left and right arm, right leg), are conditioned and digital section used for signal processing and data transmission. 

Input signal conditioning includes:
* RFI/EMI differential filtering
* First gain stage using instrumentation amplifier INA818
* High-pass filtering implemented with 1st order C-R network 
* Second gain stage
* 5th order active Butterworth low-pass filter
* Precision ADC input preconditioning - voltage follower + antialiasing filtering
* ADCs voltage reference with driver circuit

Digital section is based on STM32F407 MCU and it's used for acquiring signals from ADC using 3-Wire SPI protocol, USB, I2C and UART communication with external devices and for executing various signal processing algorithms on acquired data (e.g. Pan-Tompkins). 

</p>

![Screenshot](ECG.png)


## Usage

Project files, including schematic and PCB documents, need to be opened with Altium Designer. Gerber files are production-ready and can be reviewed with various free alternative tools. 

**Disclaimer**: This project is work in progress. Use the files, hardware, and software given in this repository at your own risk.

## Contributing
I'm currenlty writing firmware for the made PCB. It is very likely that there will be several versions of this project, so for any major or minor changes you would like to implement yourself, please open an issue so we can discuss about it or alternatively send me an email: dino.cindric@fer.hr.

Thanks you.

## License
[MIT](https://choosealicense.com/licenses/mit/) Copyright (c) 2020, Dino Cindrić - All rights reserved.