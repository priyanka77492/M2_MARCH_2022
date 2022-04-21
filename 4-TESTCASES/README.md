#include <avr/io.h>
#include <util/delay.h>

int main(void)
{
    DDRB |= 0xFF;
    TCCR1A |= 1<<WGM11 |
    1<<COM1A1 | 1<<COM1A0 ;
    TCCR1B |= 1<<WGM13 |
    1<<WGM12 | 1<<CS10; //no
    
    ICR1 = 19999;
    //18000
    while(1)
{
    OCR1A = ICR1 - 1000;
    _delay_ms(100);
}
}
