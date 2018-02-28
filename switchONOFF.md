# 8stepseq

#include <avr/io.h>

void mydelay(long int k)
{
	long int i;
	for (i = 0; i < k; i++)
	{
		asm("nop"); //no operation for one cycle
	}
}

int main()
{
	DDRB = 0b11111000; //pin 10 input, 13 output

	while(1)
	{
		if(PINB & (1<<2))
		{
			PORTB |= (1<<5);
		}
		else
		PORTB &= ~(1<<5);
	}


	return 0;
}
