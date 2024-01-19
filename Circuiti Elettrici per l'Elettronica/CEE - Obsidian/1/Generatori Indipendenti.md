## TENSIONE
Ideale: 
$v=v_s(t)$
	La tensione è indipendente dal valore della corrente nel ramo.
	Equivale ad un *cortocircuito* se  $v_s = 0$

Reale: 
metto una resistenza in serie.
	Avrà anche una resistenza di carico, che rappresenta l'utilizzatore elettrico $R_L$.  A vuoto i morsetti hanno tensione invariata $v_s$ e corrente nulla perchè CA.
$$ v_L = v_s \cdot \frac{R_L}{R_L+R_{in}}\quad i_L= \frac{v_s}{R_l+R_{in}}$$

> Se $R_{in}$ è piccola, più $R_L$ avrà la caduta di tensione effettivamente desiderata.
### Equivalenze
- La *serie* di $n$ generatori indipendenti di tensione (o batterie) è equivalente ad un generatore con tensione pari alla somma algebrica delle tensioni $$v_{eq} = \sum_k v_k$$
	Per calcolare la tensione equivalente si applica la LKT.

- Il *parallelo* di $n$ generatori è ammesso se e solo se hanno lo stesso segnale: in quel caso sono equivalenti a uno solo.
	Le correnti nei singoli rami sono indeterminate.

---
## CORRENTE
Ideale:
$i=i_s(t)$
	La corrente è indipendente dal valore della tensione nel ramo.
	Equivale ad un *circuito aperto* se  $i_s = 0$

Reale: 
metto una resistenza in parallelo.
	Avrà anche una resistenza di carico, che rappresenta l'utilizzatore elettrico $R_L$. A CC la tensione è nulla perchè la corrente passa lì e non sul resistore interno.
$$ i_L = i_s \cdot \frac{G_L}{G_L+G_{in}}\quad v_L= R_{L}\cdot i_L$$

> A causa del partitore di corrente, si cerca stavolta una $R_{in}$ elevata così da far scorrere èiù corrente possibile sul carico.
### Equivalenze
- Il *parallelo* di $n$ generatori indipendenti di corrente è equivalente ad un generatore con corrente pari alla somma algebrica delle correnti $$i_{eq} = \sum_k i_k$$
	Per calcolare la corrente equivalente si applica la LKC (attenzione alle polarità).

- La *serie* di $n$ generatori è ammessa se e solo se hanno lo stesso segnale: in quel caso sono equivalenti a uno solo.
	Le tensioni nei singoli rami sono indeterminate.

## Combinazioni 

Quando si ha un *parallelo* di tensione e corrente, vince il *gen. di tensione* e la corrente è imposta dal circuito.
![[Pasted image 20240105102917.png]]

Quando si ha una *serie* di tensione e corrente, vince il *gen. di corrente* e la tensione è imposta dal circuito.
![[Pasted image 20240105103025.png]]


## Trasformazioni

Vedi [[Thevenin-Norton]] per la generalizzazione.
![[Immagine WhatsApp 2024-01-05 ore 10.42.49_f8bed790.jpg]]