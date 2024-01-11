Fa riferimento alla tecnologia [tMOS|nMOS ad arricchimento].

## Tecnologia
Usa due MOSFET ad arricchimento realizzati nello stesso blocchetto di silicio e canali a polarità opposta che lavorano complementariamente.

![[Pasted image 20231101223847.png]]

## Modello
![[Pasted image 20231101223952.png]]

Vedi [[Interfacciamento TTL CMOS]].
### Vantaggi rispetto a BJT??

- Maggiore densità di integrazione - non servono le resistenze xk c'è la regione ohmica; è più miniaturizzabile
	- Ha un range di alimentazione migliore - di nuovo, non servono resistenze quindi posso dargli più corrente
- Si realizza con meno passaggi

- Consumi! Ha una dissipazione statica trascurabile (consumo statico = 0 grazie all'assenza di percorsi alimentazione - massa); per il consumo dinamico:
![[Pasted image 20231101223916.png]]

- Ha comportamento simmetrico, quini "0" e "1" hanno livelli elettrici complementari

- Reagisce meglio alla temperatura, ha compesazioni termiche

### Debolezze
- Sono più lenti, hanno quella capacità in ingresso stupidina $C_{in}$
- Sono sensibili alle scariche elettrostatiche se la capacità in ingresso è troppo piccola

- Fenomeno di **LATCH-UP**, si innesca un percorso di conduzione che una volta aperto non si spegne mai e rompe tutto. Succede quando miniaturizzo troppo, perchè delle zone vicine dei due gate (n e p) sono troppo piccole, diventano tutte RCS e quindi sminchiano e conducono;
	=> si risolve con dei drogaggi di guardia

## Comportamento
Questo è il grafico della caratteristica:
![[Pasted image 20231102093141.png]]
(slide 34)

A: $V_{in}<V_{t} \quad \rightarrow \quad I=0$              pMOS zona ohmica, nMOS off $V_{out}=V_{dd}$
B: $V_{t} <V_{in}<V_{dd}-V_{t}$                  pMOS zona ohmica, nMOS saturazione
C: $V_{t} <V_{in}<V_{dd}-V_{t}$                  pMOS saturazione, nMOS saturazione (max consumo)
D: ''                                               pMOS saturazione, nMOS zona ohmica
E: $V_{in}>V_{dd}-|V_{t}| \quad \rightarrow \quad I=0$   pMOS off, nMOS zona ohmica, $V_{out}=0$

## Famiglia 74HC
Ha delle *caratteristiche statiche* ideali:
- $2V < V_{cc} < 6V$              <- compatibile coi $5V\pm10$% del TTL

- VALORE LIVELLI:
    $V_{oh}=99$% $V_{cc}$
    $V_{ol}=1$% $V_{cc}$
    $V_{ih}=70$% $V_{cc}$
    $V_{il}=30$% $V_{cc}$

- Assorbe poca potenza

Per le *caratteristiche dinamiche* invece fa un po' più cacare, ha tempi doppi di propagazione rispetto al 74LS, ha circa $20ns$ sia in ingresso che in uscita