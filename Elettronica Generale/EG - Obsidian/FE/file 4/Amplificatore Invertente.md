Configurazione dell'[[Amplificatore Operazionale]]
Si chiama Amplificatore invertente di Tensione, e si realizza configurando l'AO con reazione negativa. Di seguito uno schema del circuito:
![[Pasted image 20231025145208.png]]

#### Configurazione
>DEF: la **reazione negativa** è un percorso realizzato tra l'uscita $V_{out}$ e l'ingresso $V_{-}$ dell'AO stesso.

La presenza di $R_{2}$ abbassa la tensione nel punto dove si legge $V_{out}$ 
$\Rightarrow$ anche perchè la corrente relativa al segnale in entrata $V_s$ non può spezzarsi ed entrare nell'AO, per cui finirà tutta sulla resistenza $R_2$.
##### Funzionamento reazione negativa
0. Inizialmente si ha $V_{-}> V_{+}$ perchè $V_{+} = GND$
   $\Rightarrow$ $V_{out} = -V_p$  perchè i due ingressi sono ABBASTANZA diversi e quindi si lavora in saturazione.
1. il segnale $-V_p$ va a far diminuire il valore al morsetto $V_-$ per cui si avvicina al valore di $V_+$ 
2. la retroazione dunque tende a far avvicinare $V_-$ e $V_+$ fino alla quasi coincidenza


#### Caratteristiche
- Il *segnale in uscita* si calcola come
$$V_{out}= - V_{s}\,\cdot\, \frac{R_2}{R_1}$$
Non entra corrente nel terminale meno $\Rightarrow$ $I_2$ scorre in entrambe le resistenze: $$\begin{align} I_{2} &= \frac{(V_{s}-0)}{R_{1}}= \frac{V_{s}}{R_{1}}\\ I_{2} &= \frac{(0-V_{out})}{R_{2}}= - \frac{V_{out}}{R_2} \end{align}$$
Per cui l'ipotesi in funzionamento di **amplificatore invertente** è:
$$\frac{V_s}{R_{1}}= -\frac{V_{out}}{R_{2}}$$
Oppure di nuovo $V_{out}= - V_{s}\,\cdot\, \frac{R_2}{R_1}$ 

**NB**: posso pilotare l'amplificazione del segnale in entrata usando i valori delle resistenze (o i carichi che metto) $\Rightarrow$ programmo un $R_{2} >>> R_{1}$ 

---
- La corrente che l'AO può scambiare all'esterno è $I_{out} \sim \infty$ ... In realtà c'è un tetto massimo:
	L'AO cerca di mantenere $V_{out}= V_{in}$ quindi so che posso scoprire la corrente che dovrà erogare facendo $I_{out} = I_{2} \sim \frac{V_{out}}{R_2}$ $\Rightarrow$ non posso avere carichi troppo piccoli a pari tensione perchè altrimenti faccio esplodere tutto.
	
	>Esempio da appunti:![[003.png]]
##### Comportamento non a vuoto
Se sostituissi le resistenze con delle impedenze: $$V_{out}= -V_s\,\cdot\,\frac{Z_2}{R_1}=-V_{s}\,\cdot\,\frac{1}{j\omega RC}=-\frac{1}{RC}\int V_s$$
#### Perchè invertente?
Proviamo a progettare l'amplificatore invertente.

Prima di tutto mando $V_+$ a GND, e mi semplifico tutti i calcoli.

Poi dico $$ \begin{align} V_{-}=& \,V_{+} = 0 \\ I_{1}=& \frac{(V_{in}-0)}{R_{1}}= \frac{V_{in}}{R_1}\end{align}$$
Ma siccome vale anche $I_1=I_{2}$ perchè $I_{in}=0$: $$I_1=I_{2}= \frac{0-V_{out}}{R_{2}}= -\frac{V_{out}}{R_2}$$
Che da $I_{1}= V_{in}/R_1$ $$ V_{out}= -V_{in}\frac{R_2}{R_1}$$
Il segno di quest'ultima identità ci da l'inversione.

---

Gli appunti OG di questa parte:
![[004.png]]![[005.png]]