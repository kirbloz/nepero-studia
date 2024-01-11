Schema a pg3 file 4.

RIASSUNTO CARATTERISTICHE:
$$\large \begin{align}
|\,I_{+\,}|\sim |\, I_{-}\,|\sim0 \quad \quad \quad \quad \quad\quad R_{in}\sim \infty \\ \\
V_{out} = V_{o}^{*}- (R_{out} \,\cdot \, I_{out}) \quad \quad \quad \quad R_{out}\sim 0 \\ \\
V_{o}^{*} = A \, \cdot \, (V_{+}-V_{-}) \quad \quad \quad \quad \quad  A > 10^{6}\sim \infty \\ \\
0 < I_{out}< I_{\text{out, max}} \sim \infty \quad \quad \quad \quad \quad \quad 
\end{align}$$

![[Pasted image 20231025000047.png]]
Un AO è realizzato utilizzando decine di transistor al suo interno, quindi semplifichiamo il modello e lo studiamo come descritto di seguito. Il grafico caratteristico è questo:
![[Pasted image 20231025000011.png]]

#### Caratteristiche

##### Alimentazione duale
- Ha due alimentazioni distinte, anzichè $V_{p}$ e GND ha: $$+V_{p}\quad \quad -V_{p}$$
$\Rightarrow$ si dice che è ad ALIMENTAZIONE DUALE.
---
##### Morsetti in Ingresso
- Ha due ingressi (in tensione): $$
V_{+}\quad \quad V_{-}
$$
e si identifica il segnale in ingresso come $V_{in}= V_{+}-V_{-}$
---
##### Corrente in ingresso
- Il modello prevede che la corrente entrante nell'AO sia NULLA$$ |\,I_{+}\,| \sim |\,I_{-}\,| \sim 0$$
> In realtà è nell'ordine dei pico Ampere

$\Rightarrow$ modellizziamo quindi una *resistenza interna* $R_{in}$ che collega gli ingessi; deve essere un'impedenza enorme per impedire l'ingresso di correnti ($\sim M\ohm$) $$R_{in}\sim \infty$$

---
##### Segnale in uscita
- L'uscita dipende dagli ingressi in tensione - $V_{in}$ - e non dalla corrente erogata $I_{out}$: $$ \begin{align} R_{out} \sim 0 \quad \quad \end{align}$$
$\Rightarrow$ l'AO è in grando di mantenere la $V_{out}$ fissa in base ai valori $V_{in}$ pur erogando una qualsiasi corrente. Questo aiuta a supportare tante porte logiche in serie / parallelo ma soprattutto ci invita a definire l'upper bound di $I_{out}$ come:
$$I_{out}\,\,< \,\,I_{out\,max}\sim \infty$$

---
##### Range segnale in uscita
- La $V_{out}$ è pilotata ma deve sempre rispettare la relazione che determina il range di valori per la tensione in uscita:$$\begin{align} -V_{p}\,\,< V_{out}\,\,< +V_{p} \quad\quad \\ V_{out} = A \,\,\cdot \,\,V_{in} \quad \quad \quad A \sim 10^{6} \end{align}$$
$\Rightarrow$ $A$ è il coefficiente di amplificazione del segnale.
$\Rightarrow$ ci indica che il AO funziona bene (o amplifica bene) a bassi segnali in entrata



#### Note 

<< Funziona sia in DC che AC, passa banda infinita.

<<Essendo $A \sim 10^6$, il dispositivo rimane fuori dalla saturazione (uscita lontana dai suoi estremi) solo se $V_{in}$ è molto piccolo. Dunque se $V_{+}\approx V_{-}$ 
Per avere grandezze nell'ordine dei Volt in uscita, lo sbilanciamento tra $V_+$ e $V_{-}$ deve essere minimo:
$$V_{out} \,[\sim V\,] \quad = \quad V_{in}\,\, \cdot \,\,A \quad\approx \quad(V_{+}-V_{-})\,\, \cdot \,\,10^6$$
>Se $(V_{+}-V_{-}) \sim 1mV \sim 10^{-5}$ allora avremo $V_{out} \sim 10^1$

![[Pasted image 20231024235832.png]]
$\Rightarrow$ Questo perchè GRANDE DOGMA:  $V_{out}$ deve stare nel range di alimentazione (che è $\pm 5V$ generalmente)

#### Configurazioni
- [[Amplificatore a Guadagno = 1]] (Lineare)
- [[Amplificatore Invertente]] (Lineare con reazione negativa)
- [[UNIVERSITA/CIRCUITI ED ELETTRONICA/FE/file 4/Comparatore]] (Saturazione)
	- se a isteresi, saturazione con reazione positiva

DEF: la **reazione positiva** è un percorso realizzato tra l'uscita e l'ingresso $V_{+}$ dell'AO stesso.
DEF: la **reazione negativa** è un percorso realizzato tra l'uscita e l'ingresso $V_{-}$ dell'AO stesso.

![[01.png]]


#### Osservazioni
Ultima slide del blocco:

- Se l'AO è alimentato in $[\,-V_{ee}\,;\,+V_{cc}\,]$ allora non potrà riceve segnali $V_{in}$ fuori da questo range
	- Le uscite che produce stanno tra $[\,-V_{ee} + 0.7V\,;\,+V_{cc}- 0.7V\,]$;
	- I dispositivi rail2rail mantengono il range IN - OUT inalterato;

- Esistono dispositivi comparatori che hanno l'uscita con un transistor a collettore aperto (scelgo la tensione di "1" con la rete di polarizzione esterna del collettore)

- Esistono dispositivi ad alimentazione singola più semplici per l'utilizzo nei sistemi che integrano dispositivi analogici e digitali