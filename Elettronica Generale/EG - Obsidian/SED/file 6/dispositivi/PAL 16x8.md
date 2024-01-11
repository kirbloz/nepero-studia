Due dispositivi SPLD a tecnologia PAL.
![[Pasted image 20231201163513.png]]


## 16L8
La più famosa.
Ha fino a 16 ingressi e 8 uscite. Ma come fa se ha solo 20 pin di cui 1 di alimentazione e 1 di massa?

Perchè ha una architettura che sta alla base della GPIO: 
![[Pasted image 20231202113426.png]]
Vediamo che lo stadio di uscita di questo PIN gli permette di comportarsi sia come OUT che come IN.
>Quando il tristate è abilitato diventa OUT
>Quanti pterms in una OR? 7

- Si usa per MUX, sommatori, comparatori
- Macchine asincrone
## 16R8
Ha dei flip flop in uscita. CLK al primo pin. Immediatamente successivo a 16L8.
- Perde un PIN per poter leggere il CLK
- Perde flessibilità perchè il controllo del tristate è fisso sul pin 11
![[Pasted image 20231202113749.png]]
- Ogni uscita è sincronizzata al CLK

Lo stadio di uscita si trasforma, invece del tristate singolo, abbiamo un FF che lo precede.
![[Pasted image 20231202113735.png]]

- Si usa per realizzare temporizzatori, contatori, sequenziatori, shift register. Tutte le macchine sincrone a 8 bit.
  E' un dispositivo generale per macchine singole fino a saturazione del fan-in delle OR.