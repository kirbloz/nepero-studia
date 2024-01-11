## Scenario
![[Pasted image 20231110175025.png]]![[Pasted image 20231110175058.png]]

Staticamente la porta 1 impone livelli fupori dalla regione d'incertezza.. ma durante la commutazione? Non è istantanea!

Se le porte son realizzate con la stessa tecnologia, allora il tempo di commutazione di 1 è quasi istantaneo rispetto al tempo di reazione della porta 2, che non reagisce alla regione d'incertezza.

Se la porta 1 è molto più lenta: la porta 2 avrà un'uscita non predicibile.

---
Zoom su quello che succede:
![[Pasted image 20231110175837.png]]

il segnale transita nella zona d'incertezza per un certo periodo di tempo. Se il disp B ha un tempo di reazione superiore a quel tempo.. Potrebbe dare in uscita:
![[Pasted image 20231110175815.png]]
USCITA NOT: In corrispondenza di un fronte di discesa ne ho due giu e uno su!
![[Pasted image 20231115112554.png]]
### Condizione 
La commutazione di A deve essere *abbastanza veloce* poichè B non possa creare altre commutazioni.
Dunque inferiore al tempo di reazione di B.
>I segnali passano sempre per la zona di incertezza, ma se ci rimangono per MENO tempo rispetto al tempo di reazione dei ricevitori, tutto ok, non fanno tempo ad accorgersene

**Problema**: solo se il pilota è lento e il ricevitore è veloce.
>Esempio: a volte anche con A veloce, se esistono in mezzo delle capacità parassite, l'effetto è lo stesso. Problema dell'ingresso capacitivo dei cMOS