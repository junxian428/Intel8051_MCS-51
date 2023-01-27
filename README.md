# Intel8051_MCS-51

STC-ISP

https://drive.google.com/file/d/181dQm74dqHOtwJ1xHH-m3F1PRy_UHPR5/view?usp=sharing

ZIP FIlE (For Setup environment link)

https://drive.google.com/file/d/1R_qc5Gvxh5u0cpx-k4B9j3E6ZkXo9cPW/view?usp=sharing


————————————————————————————————————————————————————————————————————————————————————————————————

LED Blinking


#include <REGX52.H>


void main(){

	P2 = 0x55;//0101 0101
	
}

Demo

![324889906_724584315953581_7879092369628124297_n](https://user-images.githubusercontent.com/58724748/215066076-365aa9e7-66aa-42a6-96e7-0403fbf7d4b9.jpg)


Environment Setup

![Screenshot (404)](https://user-images.githubusercontent.com/58724748/215066117-d57dd54f-40d4-4f97-b6ca-203d4c32228e.png)

_______________________________________________________________________________________________

Delay LED Blinking 

#include <REGX52.H>

#include <INTRINS.H>

void Delay500ms()		//@12.000MHz
{

	unsigned char i, j, k;

	_nop_();
  
	i = 4;
  
	j = 205;
  
	k = 187;
  
	do
  
	{
  
		do
    
		{
    
			while (--k);
      
		} while (--j);
    
	} while (--i);
  
}

void main(){
	
	while(1){
		
		P2 = 0xFE;
    
		Delay500ms();
    
		P2 = 0xFF;
    
		Delay500ms();

	}
}
