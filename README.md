# mbed LCD library for the mbed application board / shield


## Example

Here is an example for the application board with the mbed for mbed 6
```cpp

//C12832GR
//Version compatible MBED-0S 6
//
/* mbed Microcontroller Library
* Exemple afficheur C12832 de la MBED Application shield
* Attention une des broche de l'afficheur est partage avec
* la led verte (LED1) de la carte NUCLEO F446RE !
*/
#include "mbed.h"
#include <cstdio>
#include "C12832.h"
C12832 lcd(D11, D13, D12, D7, D10);
int main(){
    float j=0;
    lcs.cls();
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
