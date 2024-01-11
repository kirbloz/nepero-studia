Analizziamo problemi di Interfacciamento.

## Problema AO 
Nelle famiglie logiche bipolari RTL, DTL, TTL abbiamo questa caratteristica: gli [[Amplificatore Operazionale|amplificatori operazionali]] sono progettati in modo da avere $R_{in}\sim \infty$ e $R_{out}\sim 0$, per avere una migliore amplificazione ed erogazione di corrente sufficiente a mantenere la tensione voluta.

Purtroppo quest'impedenza nulla in uscita crea dei problemi quando si trova una configurazione di conduzione di questo tipo:
![[Pasted image 20231115102901.png]]
La corrente (molto elevata) scorre in entrambi gli AO friggendoli e danneggiandoli. Nelle RTL, DTL, TTL si era risolto il introducendo una *resistenza di pull-up* intermedia ai due componenti, ma questo causava il peggioramento dei livelli di uscita dei segnali.

## Problema generale
Interfacciamento tra due dispositivi: come si realizza il collegamento tra **due uscite**?
![[Pasted image 20231111103825.png]]

<span style="background:#ff4d4f">Non posso connetterli direttamente perchè i dispositivi digitali hanno *bassa impedenza in uscita* => percorso a bassa impedenza tra alimentazione e GND.</span>

Con riferimento alla figura là sopra:
- Nel NOT1 entra "0" ed esce "1". 
Dunque vedremo nello stadio IN delle correnti di perdita erogate $I_{il}$ e nello stadio OUT è erogata una $I_{oh}$ attraverso la $R_{op}$.

- Nel NOT2 entra un "1" ed esce uno "0". 
Assorbe una $I_{ih}$ nello stadio IN, che va a ricaricare $C_{in}$. Dallo stadio OUT è assorbita una $I_{ol}$ attraverso $R_{og}$.

Con questo collegamento NOT2 assorbe la corrente dell' "1" che NOT1 eroga tramite $R_{op}$, poi la scarica attraverso $R_{og}$. 
Dunque chiamiamo $I_{p}$ la corrente che scambiano:
$$\large \begin{cases} I_{oh} = \frac{V_{p}}{R_{op}}\\ I_{ol}= \frac{V_{p}}{R_{og}}\end{cases} \quad\Rightarrow I_{p}=\frac{V_{p}}{R_{op}+R_{og}}$$

La linea (?data bus?) che li unisce si porta ad una tensione di partitore: $V= V_{p}\cdot \frac{R_{og}}{R_{og}+R_{op}}$

*Assunzione*: $R_{op}=R_{og}$ ma allora $V=V_{p}/2$ e questo significa che la linea ha un valore nella *zona di incertezza*!

## Soluzioni
### Open Collector
Vedi [[Open Collector]]
Esistono dei dispositivi con uscita a collettore aperto, hanno due uscite possibili: "0" e "Z" (alta impedenza).

### Tri-state
 Vedi [[Tri-state]]

## Confronto soluzioni

3S:
- piu veloce (sfrutta lo schema complementare)
- più disponibilità di IC
- Fan-Out limitato
- non adatto al multiutente
	- propaga il guasto ed è complesso

OC:
- più lento, solo da "0" a "1" (dipende da R pull-up)
- è un line driver
- elevato Fan-Out in base a R pull-up
- affidabile per pilotare le linee
	- più semplice, non propaga guasti