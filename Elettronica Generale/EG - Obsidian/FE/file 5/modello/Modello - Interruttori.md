Ipotizziamo di avere degli interruttori ideali, quindi che si comportano come una resistenza nulla (chiuso) o infinita (aperto).

Sotto le analisi dei singoli, un riassuntino.
## A - Identità
Osserviamo di nuovo il suo comportamento con:
$V_{p}$, $I_{o}$ di alimentazione; IN comando; e $R_{l}$ come resistenza (carico per evitare CC interno).

-- IN="0" -- 
Non scorre corrente dal generatore $V_{p}$ ma la corrente dal carico va a massa dunque la tensione del nodo OUT non è GND.
$V_{out} =R_{l}\cdot I_{o}$
$V_{in} = 0 \rightarrow R_{eq}=\infty$
=> OUT="0" debole

-- IN="1" --
Si crea un collegamento tra alimentazione e massa; il punto "medio" identificato da OUT si ritroverà a tensione $V_{p}$ che scaricherà tutta quanta con la corrente su $R_{l}$ verso GND.
$V_{out}= + V_{p}$
$V_{in} = +V \rightarrow R_{eq}=0$
=> OUT="1" forte

![[UNIVERSITA/CIRCUITI ED ELETTRONICA/SED/imgs/Pasted image 20231031230027.png]]

## B - Identità
Osserviamo il  comportamento con:
$V_{p}$, $I_{o}$ di alimentazione; IN comando; e $R_{l}$ come resistenza verso GND (carico per evitare CC interno) accompagnata da $R_{h}$ verso alimentazione.

-- IN="0" -- 
Interruttore aperto non scorre corrente dal segnale $+V_{p}$. Tuttavia c'è la corrente del carico che si spegne su GND quindi la tensione di OUT non è nulla.
$V_{out}=GND + I_{o}\cdot R_{l}$
$V_{in}=0$ 
=> OUT= "0" debole

-- IN="1" -- 
Interruttore chiuso e scorre corrente da $+V_{p}$ verso $R_{l}$ e GND. Dunque il valore di tensione del punto OUT *dipende* dal valore delle resistenze $R_{h}$ ed $R_l$, come d'accordo alla legge del partitore di tensione.
Supponiamo per semplicità che le resistenze siano medesime e pari a R.
$V_{out}= (V_{in}-I_{o\cdot}R) \cdot \frac{1}{2}$
$V_{in}=+V_{p}$ 
=> OUT= "1" forte con una debolezza*
>Debole in base alle resistenze che posso programmare in valore in fase di progettazione.

>Commento: si cerca una $R_{h}>> R_{l}$ sia per avere una trasmissione del segnale con guadagno più vicino all'1 possibile; ma anche perchè $R_{l}$ è ciò che indebolisce lo zero e quindi più piccola è quella resistenza, più bello sarà lo zero.

![[UNIVERSITA/CIRCUITI ED ELETTRONICA/SED/imgs/Pasted image 20231031230058.png]]
## C - NOT
Osserviamo il  comportamento con:
$V_{p}$, $I_{o}$ di alimentazione; IN comando; e $R_{h}$ verso alimentazione (carico per evitare CC interno).

-- IN="0" -- 
Interruttore aperto, dunque non esiste un percorso tra alimentazione e massa. La corrente dovrà scorrere "tutta" attraverso il nodo OUT dunque la caduta di tensione ai capi di $R_h$ sarà la caduta che interessa l'uscita.
$V_{in} = + V_{p}$
$V_{out} = +V_{p}-R_{h}\cdot I_{o}$
=> OUT= "1"  indebolito
>L'"1" è indebolito dalla presenza di $R_{h}$ (anti-CC), ma è una resistenza essenziale, che non potrà essere a valore troppo basso - se passa "tanta" corrente si rompe il componente - nè troppo alto - rovina la codifica, consuma troppo.

-- IN="1" -- 
L'interruttore si chiude permettendo alla corrente di alimentazione di scaricare su GND.
Questo significa che GND e OUT saranno allo stesso valore potenziale.
$V_{out} = GND$
=> OUT= "0" bellissimo
>La $I_o$ si può considerare infinita

![[Pasted image 20231031230741.png]]
## D - NOT
Questa è una variante di B, ne sposta l'uscita PRIMA dell'interruttore.
Così realizza la funzione NOT.

-- IN="0" -- 
Interruttore aperto, non esiste un percorso da alimentazione verso massa, dunque tutta la $I_{o}$ scorre verso OUT.
$V_{in} = +V_{p}$
$V_{out}= V_{p}-R_{h}\cdot I_{o}$
=> OUT="1" indebolito come C

-- IN="1" -- 
Interruttore chiuso, si crea un percorso tra massa ed alimentazione che attraversa le due resistenze. Il punto OUT avrà potenziale determinato dal partitore di tensione applicato su $R_{h}$ ed $R_{l}$
$V_{in} = +V_{p}$
$V_{out}=V_{in} \cdot R_{h} / (R_{h}+R_{l})$
=> OUT= "0" indebolito

>Siccome cerco un $V_{out}\sim 0$ mi interessa avere il rapporto $R_{h} / (R_{h}+R_{l}) \sim 0$ dunque in fase di progettazione si sceglie una $R_{h}<<R_{l}$

- Per semplicità assumiamo $R_{l}=R_{h}=R$ dunque diventa:$$V_{out}= V_{in}\cdot 1 /2$$
![[Pasted image 20231101092747.png]]
## E - NOT SIMMETRICO
Questo interruttore invece è un po' più elaborato, è più fico. Perchè esistono due resistenze si, ma la corrente non le attraverserà mai entrambe. Ha un comportamento perfettamente simmetrico.

Posso rendere le R resistenze *piccole quanto voglio* perchè tanto non ci sarà mai rischio di CC.
Ottimo! Consumo di meno e indebolisco di meno i livelli. 

>Nota: primo interruttore è !IN, il secondo è IN

-- IN="0" -- 
Il primo interruttore è chiuso, il secondo è aperto.
Esiste un percorso per la corrente da alimentazione a OUT attraverso $R_h$.
$V_{in}= +V_{p}$
$V_{out}=V_{p}-I_{o}\cdot R_{h}$
=> OUT= "1" indebolito (meno)

-- IN="1" -- 
Il primo interruttore è aperto, il secondo è chiuso.
Non esiste un percorso per la corrente da alimentazione a massa, dunque la tensione letta in OUT sarà GND aumentata dalla caduta della corrente di carico su $R_{l}$.
$V_{out}= GND + R_{l}\cdot I_{o}$
=> OUT= "0" indebolito (meno)

![[Pasted image 20231101093832.png]]

## RIASSUNTO
Negli schemi a interruttori, ipotizzando interruttori ideali si possono fare queste osservazioni.

- La tensione di uscita $V_{out}$ dipende dalla corrente di uscita $I_{o}$ a "0" e/o a "1"
- La corrente $I_{o}$ è erogata dal dispositivo (OUT="1") o assorbita (OUT="0")
- $I_{o}$ corrisponde circa alla somma delle correnti $I_{Li}$ richieste dai carichi $Li$ per poter funzionare
- I carichi sono altri dispositivi digitali -> Vedi [[Modello Statico#Stadio IN e OUT]]
- <span style="background:#fff88f">Le architetture simmetriche, come E, assicurano piena complementarietà</span>


>Nota: assorbita implica che la corrente dissipa su una resistenza interna al dispositivo; erogata implica che se ne va a GND del carico.