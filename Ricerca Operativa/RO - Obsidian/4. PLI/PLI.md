Glossario:
- [[#Definizione]] con rimandi a [[Convex Hull]] e [[Upper e Lower Bound]]
- [[#Modellizzazione]], alcune tecniche ed esempi
- Vedi in seguito [[UM]]
- Vedi anche [[#Risoluzione]]


# Definizione
Un problema di ottimizzazione discreta (di minimo) è un problema che cerca $x \in F$ con $F$ discreto tale che$$c(x) \leq c(y)\quad \quad\forall y\in F$$
**DEF** :
 chiamo *istanza* di un problema di ottimizzazione una coppia $(F, c)$ dove $F$ è l'insieme delle soluzioni ammissibili mentre $c$ rappresenta la funzione di costo $$c :F\rightarrow Z$$
- Se si eliminano i vincoli di interezza si ottiene il [[Convex Hull]].. Vedi la sua pagina dedicata.
- Inoltre tra formulazione PLI (X) e formulazione PL(rilassamento) c'è una relazione che lega i loro valori ottimi, in termini di limititatezza: [[Upper e Lower Bound]]

![[Pasted image 20240203191233.png]]

Le valutazioni sui UB e LB ci permettono di enunciare..

*Proposizione*: se la soluzione ottima del rilassamento continuo $x^{\ast}_{PL}$ è intera allora è ottima anche per il problema intero.

*Dim*:
 ![[Pasted image 20240203192156.png]]

---

*Osservazione*: quelli di PLI sono tutti problemi np-hard. Si usa per la risoluzione:
- algoritmi euristici - trovano ottimi locali in polin time
- algoritmi esatti - ottimo globale in exp time

Ad esempio un euristico è l'algoritmo naif di arrotondamento.
 ![[Pasted image 20240203192516.png]]


---
# Modellizzazione
Nella PL, la formulazione in generale prevede poche variabili e vincoli.. la complessità è dettata da $m$ ed $n$.
Nella PLI una buona formulazione è *un rilassato stringente più piccolo possibile*, ed è cruciale perchè potrebbe ridurre la difficoltà del problema.

**DEF**
 le *soluzioni greedy* sono risoluzioni a problemi ottenute facendo ragionamenti di carattere euristico; possono avere un qualche criterio alla base ma sono sub-ottime.

## Scelta binaria
![[Pasted image 20240203114827.png]]

- PROBLEMI DI KNAPSACK
Sono problemi NP-hard. Riempire zaino a capienza massima.
![[Pasted image 20240203114936.png]]
$x_j$ è la variabile che stabilisce quale oggetto è selezionato, e sono ordinate in modo da corrispondere agli oggetti per indici quindi ogni item, ogni $x_{j}$ sarà moltiplicata per un parametro noto identificativo dell'oggetto $v_j$ e $p_j$ 
>attenzione ad avere anche $\sum p_{j} > 0$ altrimenti potrebbe non scegliere nulla 
![[Pasted image 20240203115529.png]]

RISOLUZIONE?
1. elencare tutte le possibili combinazioni di item? $2^n$ quindi la difficoltà esplode velocemente. 
2. mi accontento di una soluzione euristica sub-ottima, ma buona e con tempi ragionevoli

=> ORDINAMENTO, complessità $O(n\cdot \log n)$
- in base al valore
- in base al costo
- in base al rapporto valore/peso
ANALISI CASO PEGGIORE: sparo a $\infty$ o $0$ alcuni vincoli, considero oggetti con parametri svergoli, in modo da forzare soluzioni del cazzo![[Pasted image 20240203120055.png]]
## Selezione da un insieme
Dato un insieme di variabili binarie $x_j$ associate ognuna ad un item $j$ di un insieme $T$ di dimensione finita, posso imporre:
![[Pasted image 20240203120153.png]]

---

- PROBLEMA DI SET COVERING
Minimizzare le stazioni da aprire per garantire la copertura (*ALMENO TOTALE*) del territorio.
![[Pasted image 20240203120423.png]]
![[Pasted image 20240203120438.png]]
![[Pasted image 20240203121056.png]]

*Dettagli*
 La matrice $A$ è fatta di $a_{ij}$ che indicano se la regione $t_i$ è coperta dalla stazione $F_j$
 - righe $\rightarrow$ regioni
 - colonne $\rightarrow$ stazioni
 - $x_i$ indica se la stazione è attivata

 Funzione obiettivo: min stazioni (c è il costo di apertura)
 ![[Pasted image 20240203120740.png]]

 Prendendo un vincolo alla volta scopro quali impianti sono  *necessari* a coprire interamente una singola regione $t_i$
 ![[Pasted image 20240203121034.png]]
 ![[Pasted image 20240203121103.png]]

---

-  PROBLEMA DI SET PARTITIONING
Minimizzare le stazioni da aprire per garantire la copertura (*ALMENO TOTALE*) del territorio ma *SENZA SOVRAPPOSIZIONE*.

Impone una condizione forte, che rende il problema difficile
![[Pasted image 20240203123220.png]]

---

- PROBLEMA DI SET PACKING
Minimizzare le stazioni da aprire *SENZA SOVRAPPOSIZIONE*. Non ci sono vincoli sulla copertura che si vuole raggiungere.
" Al massimo copro una volta sola "
![[Pasted image 20240203123324.png]]

## Decisioni dipendenti
Concetto rappresentabile con le scelte binarie:
<span style="background:#fff88f">" la decisione A (variabile x) può essere presa (x=1) se e solo se la decisione B (varibile y) è stata presa (y=1) "</span>

esempio:
 ![[Pasted image 20240203124331.png]]

*FORZARE X A SEGUIRE Y*
Una variabile $x\geq 0$ può assumere valori strettamente positivi solo se una determinata decisione è stata presa.
![[Pasted image 20240203124417.png]]

 1. $y=0$ impianto chiuso, decisione non presa $\Rightarrow \quad x\leq 0 \quad \rightarrow \quad x = 0$ l'impianto non produce quindi può essere solo che $0$

2. $y=1$ impianto aperto, decisione  presa $\Rightarrow \quad x\leq M \quad \rightarrow \quad x$  è libera ma limitata superiormente (capacità produttiva)

*FORZARE Y A RIMANERE A 0 SE X = 0??*
Se ad esempio una soluzione ottima prevedesse che un impianto non deve produrre, è opportuno che anche la variabile $y_i$ indichi che questo sia chiuso.

sfrutto la funzione obiettivo
![[Pasted image 20240203124820.png]] 
$k$ sarà il costo di apertura dell'impianto.
la funzione obiettivo cercherà di portare tutte le $y\rightarrow 0$ qualora il vincolo non forzi un $x>1$ (che implicherebbe impianto aperto)

---
<center>ESEMPI DI VINCOLI</center>

*Richiesta produttiva*
![[Pasted image 20240203125114.png]]
 La produzione NON DEVE superare l'upper bound (richiesta).
 Se conosco la richiesta $r_s$ ($s$ singolo cliente), allora posso calcolare a quanto dovrò porre la capacità produttiva $M$

*Giacenza di partenza*: vincolo di bilanciamento scorte
![[Pasted image 20240203125245.png]]


---

- PROBLEMA DEL CARICO FISSO
Devo produrre un bene in una determinata quantita, con $m$ impianti. 
Produrre nell'impianto $i$ comporta costi fissi $k$ e proporzionali alla quantità prodotta $x$. Questi vanno minimizzati.

- $k_i$ vincolato a $y_i$ (apertura)
- $c_i$ vincolato a $x_i$ (qnt prodotta)

![[Pasted image 20240203125549.png]]
> è possibile che $x_i=0$ ma $y_{i}=1$ ? ovvero è possibile pagare da aprire un impianto ma non produrci?
> no perchè la funzione obiettivo tende a schiacciare queste $y_i$ a zero se non ci sono vincoli $(x_{i}>1 )\leq My_i$ che le vogliono a 1 

---

- PROBLEMA DI PLANT LOCATION

Dati:
$m$ impianti (i)
$n$ clienti (j)
$d_j$ domanda del $j$-esimo cliente
$c_{ij}$ costo trasporto unità da $i$ a $j$ 
$k_i$ costo di setup di impianto $i$ 
$z_{ij}$ quantità da spedire da $i$ a $j$ (richiesta di $j$ soddisfatta da $i$)

![[Pasted image 20240203130032.png]]

> $M$ sarà pari alla capacità dell'impianto se c'è vincolo sulla capacità produttiva.
> Altrimenti come visto sopra sarà la somma delle richieste (= domanda complessiva del mercato)

---

- SINGLE ITEM LOT SIZE
Problema di produzione. 
Determinare il bilanciamento ottimale tra 
- costo $f$ fisso
- costo di set-up $k$ se ci fosse diventa un problema PLMI complesso

- costi di mantenimento scorte in presenza di domanda 
>$h$ costo di mantenimento scorte
>$y_0$ livello iniziale scorte (>0 sennò non inizio)

- costi di produzione <span style="background:#ff4d4f">variabile nel tempo</span>. E' importante avere un modello <span style="background:#ff4d4f">sensibile al tempo</span>, per cui la linea temporale va suddivisa in intervalli.
>ogni intervallo ha una certa domanda $r_t$ $\Rightarrow$ $M_t$ upper bound di produzione del periodo 
>$c_t$ costo variabile di produzione

![[Pasted image 20240203152422.png]]

*Dettagli*
 >PRODUZIONE MENO FREQUENTE: set up ridotto, mantenimento scorte elevato
 >PRODUZIONE PIU FREQUENTE: set up elevato, mantenimento scorte ridotto

 Mi interessa minimizzare i costi che in totale sono:
 ![[Pasted image 20240203152024.png]]

 Le variabili decisionali sono:
 ![[Pasted image 20240203152339.png]]

 I vincoli che si pongono:
 - sempre sulla capacità produttiva $x_{t}\leq M_t\delta_t$
 - non negatività produzione e scorte $x$ e $y$
 - vincolo di bilanciamento scorte $y_{t}=y_{t-1}+x_{t}-r_{t}$ perchè le scorte alla fine del periodo $t$ sono quelle iniziali, più qnt prodotta, meno la domanda (richiesta clienti)

## Vincoli disgiuntivi

**DEF** :
 due vincoli sono detti *disgiuntivi* tra loro quando c'è questa relazione di attivo/non attivo
![[Pasted image 20240203153206.png]]
>attivo: soddisfatto ottimalmente, non attivo: sempre soddisfatto, ridondante

Sfruttando le [[#Decisioni dipendenti|variabili decisionali binarie]] posso fare in modo che non siano mai attivi nello stesso momento.
![[Pasted image 20240203153305.png]]
![[Pasted image 20240203153427.png]]
![[Pasted image 20240203153350.png]]

<center>GENERALIZZAZIONE</center>
COEFFICIENTI NON NEGATIVI
Dati $m$ vincoli $a^{\intercal}_{i}x \geq b_i$ con $a_{i}\geq 0$, si vuole che *siano soddisfatti esattamente $k$ vincoli*. Siccome $y_i$ è al più $1$, le possiamo usare per contare i vincoli attivi.
![[Pasted image 20240203153546.png]]

COEFFICIENTI QUALSIASI
Dati $m$ vincoli $a^{\intercal}_{i}x \geq b_i$ con le componenti di $a_{i}$ libere in segno, si vuole che *siano soddisfatti esattamente $k$ vincoli*. Siccome $y_i$ è al più $1$, le possiamo usare per contare i vincoli attivi.
![[Pasted image 20240203153648.png]]
![[Pasted image 20240203153731.png]]

---

- PROBLEMA DI JOB SEQUENCING
Suppongo di avere una macchina che deve svolgere più job in sequenza senza possibilità di parallelo. Ho un orizzonte temporale suddiviso in intervalli.
*Voglio minimizzare il tempo impiegato per svolgere tutti i job*
$a_j$ durata lavoro $j$ esimo
$d_j$ tempo mssimo per completare job $j$ esimo
$x_j$ variabile decisionale, istante di inizio del job $j$ esimo

![[Pasted image 20240203155553.png]]

---

I vincoli di tempo e sequenzialità:
![[Pasted image 20240203154725.png]]
Non parallelismo:
![[Pasted image 20240203154741.png]]
Che traducendo l'oppure in vincoli disgiunti diventa:
![[Pasted image 20240203154757.png]]
$y_{ij}$ indica se il job $i$ sarà dopo di $j$
funzionamento:
 ![[Pasted image 20240203154827.png]]

Trucco a [[appunti per esercizi#Modellizzazione]]

## Dominio discreto numerabile
Se condisero solo un insieme finito di valori, tra cui ne va generato uno solo.. il problema si riconduce ad un problema di knapsack.
![[Pasted image 20240203161318.png]]
ok cagata, uso le variabili binarie

---

<center>SOS1</center>
Se considero di generare un valore tra quelli identificati da funzioni lineari a tratti?
Si modellizza una spezzata le cui coordinate sono $(a_{i},f(a_{i}))$ e individuano i vari intervalli.

" Generare valori dentro intervalli, noti gli estremi " => combinazione convessa
![[Pasted image 20240203161603.png]]
![[Pasted image 20240203162412.png]]

<center>COSTRUZIONE</center>

Solitamente sono noti i punti di passaggio $f(a_{i})$ dove si cambia definizione di $f$.
*Nota*: con $n$ punti ho $n-1$ intervalli. <span style="background:#ff4d4f">Solo uno è attivo alla volta</span>. $n-1$ variabili binarie $y_i$
$$\sum\limits y_{i}=1$$
Dovrà quindi vincolare i valori dei coefficienti per la combinazione convessa $\lambda_{i}$ e $\lambda_{i+1}$ $\in\,[\,0,1\,]$ da cui ricavare il valore (chiamiamolo $x$). La <span style="background:#ff4d4f">funzione obiettivo genera</span> il valore per cui:
$$f(x)=\sum\limits\lambda_if(a_i)$$

Le $\lambda$ sono variabili decisionali (associate ad ogni $a_i$, estremi degli intervalli di definizione) che <span style="background:#ff4d4f">possono assumere un valore non nullo SE E SOLO SE la $y_i$ di un'intervallo (precedente o successivo) a loro adiaciente è attiva</span>.
$$\lambda_{i}\leq y_{i-1}+y_{i}\quad \quad i=2\dots n-1$$
Per il primo intervallo    $\lambda_{1}\leq y_1$    e l'ultimo    $\lambda_{n}\leq y_{n-1}$

![[Pasted image 20240203163440.png]]
Per poter svolgere la combinazione convessa correttamente serve che la loro somma sia 1 e entrambi positivi
$$\sum\limits\lambda_{i}=1\quad \quad \lambda_{i}\geq0\quad \quad  \forall i=1\dots n-1$$

modello:
 ![[Pasted image 20240203163603.png]]

<center>SOS2</center>
Genera sempre a partire da funzioni a tratti. Al massimo 2 variabili binarie di un insieme dato *possono essere selezionate* e *devono essere consecutive*: perchè ognuna di queste indica l'attivazione di un estremo dell'intervallo considerato.
>Praticamente non ho $y_{i}\rightarrow$ intervallo $i$, bensì $y_{i},y_{i+1}\rightarrow$ intervallo $i$. perchè si legano direttamente agli estremi

![[Pasted image 20240203163818.png]]
infatti ho vincoli di attivazione dei $\lambda_i$ più semplici ma in aggiunta ci sono dei vincoli di sequenzialità.
![[Pasted image 20240203163928.png]]




# Risoluzione
Vedi [[Algoritmi PLI]]