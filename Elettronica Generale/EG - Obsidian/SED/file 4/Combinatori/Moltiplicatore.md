Prenderemo in esempio un 4 * 4 bit multiplier. Sono usati molto poco, meglio realizzare con un FPGA.


- Può avere architettura sincrona o asincrona
- Ingressi 0-3 per A e B
- Uscite? $4+ 4=8$ bits, quindi 0-7

E' possibile connettere in sequenza con sommatori più moduli di questo tipo.
>Full HW: 
>4 moltiplicatori 2x2 bit
>1 somamtore 4 bit con shifter
>1 sommatore 8 bit

Il primo sommatore fa $R=Al\,Bh$ mentre il secondo $R+Ah\,Bh$ concatenato a $Al\,Bl$

![[Pasted image 20231203185128.png]]