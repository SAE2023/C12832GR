# mbed LCD library for the mbed application board / shield


## Example

Here is an example for the application board with the mbed lpc1768 for mbed 6
```cpp

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
