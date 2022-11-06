# mbed LCD library for the mbed application board / shield

This library is for the LCD of the mbed application board and shield 
https://developer.mbed.org/components/mbed-Application-Board/ and https://developer.mbed.org/components/mbed-Application-Shield/<br>
It uses better algorithms (Bresenham) for the graphics than the original library.


## Installation

1. "Download":https://github.com/sstaub/C12832A1Z/archive/master.zip the Master branch from GitHub
2. Unzip and modify the folder name to "C12832A1Z"
3. Move the modified folder on your Library folder (On your `Libraries` folder inside Sketchbooks or Arduino software)


## Example

Here is an example for the application board with the mbed lpc1768 for mbed 6


//C12832GR
//Version compatible MBED-0S 6
//
/* mbed Microcontroller Library
* Exemple afficheur C12832 de la MBED Application shield
*/
#include "mbed.h"
#include <cstdio>
#include "C12832.h"

#define WAIT_TIME_MS 500 
DigitalOut led1(LED1);
C12832 lcd(D11, D13, D12, D7, D10);
int main(){
    float j=0;
    lcd.locate(0,3);
    lcd.printf("mbed application shield!");
    while (true)
    {
         lcd.locate(0,15);
         j=j+0.1;
        lcd.printf("Counting : %f",j);
        wait_us(1000000);
    }
}
