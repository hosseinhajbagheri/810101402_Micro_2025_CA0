# 810101402_Micro_2025_CA0
CA0 MICRO
<img width="1920" height="1080" alt="Screenshot (724)" src="https://github.com/user-attachments/assets/686998f2-14bb-4d57-8b7e-75010f5eda11" />
<img width="1920" height="1080" alt="Screenshot (723)" src="https://github.com/user-attachments/assets/ec20fd49-272e-481c-99bf-7be41f0fb86c" />

<img width="1920" height="1080" alt="Screenshot (721)" src="https://github.com/user-attachments/assets/397dd57a-9d90-4e05-a854-b1056b34c188" />
<img width="1920" height="1080" alt="Screenshot (722)" src="https://github.com/user-attachments/assets/ff5e3542-6f98-4b6b-a207-65520820fe86" />






#include <stm32f10x.h>
void delay_ms(uint16_t t) {
	volatile unsigned long l = 0;
		for(uint16_t i = 0; i < t; i++)
			for(l = 0; l < 6000; l++)
			{ }
}
int main()
{	
		RCC->APB2ENR |= 0xFC; /* Enable clocks for GPIO ports */
			GPIOA->CRL = 0x88833344;
			GPIOA->ODR  |=  (1<<5) | (1<<6) | (1<<7);
				while(1)
		{
			int btn1 = ((GPIOA->IDR & (1<<5)) == 0);
			int btn2 = ((GPIOA->IDR & (1<<6)) == 0);
			int btn3 = ((GPIOA->IDR & (1<<7)) == 0);
			
			if ( btn1 == 1){
				GPIOA->ODR |= (1<<2);
				}
				else
				GPIOA->ODR  &= ~(1<<2);
			if  ( btn2 == 1){
				GPIOA->ODR |= (1<<3);
				}
				else
				GPIOA->ODR  &= ~(1<<3);
			if  ( btn3 == 1){
				GPIOA->ODR |= (1<<4);
				}
				else
				GPIOA->ODR  &= ~(1<<4);
				delay_ms(100);
		}			
}













