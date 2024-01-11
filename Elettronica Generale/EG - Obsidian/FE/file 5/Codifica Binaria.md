Questo file è un commento alla logica elementare di base

Serve attenzione speciale nella fase di progettazione della codifica e codifica stessa del segnale.

**DEF**: La **codifica** si assicura che le informazioni siano trasportate attraverso i circuiti di elaborazione correttamente. 
Dunque combatte il problema del rumore.
Ma si occupa anche di *distinguere* i livelli, e stabilire bene quanto "0" ed "1" sono separati sul range di valori.

Vedi anche [[Livelli interruttori]]
Modello di riferimento:
![[Pasted image 20231101143632.png]]
### Convenzioni
![[Pasted image 20231031232718.png]]

### Significato dei livelli di tensione

#### **OUT**
Generare "0" con una porta logica equivale
- ad erogare una tensione tra GND-$V_{ol}$  
- a scambiare una corrente tra 0-$I_{ol}$ 

Generare "1" con una porta logica equivale
- ad erogare una tensione tra $V_{oh}$-$V_{p}$
- a scambiare una corrente tra 0-$I_{oh}$ 
#### **IN**
Leggere "0" con una porta logica equivale
- applicare una tensione tra GND-$V_{il}$
- a scambiare una corrente tra 0-$I_{il}$
L’uscita precedente deve essere un buon “0” quindi $V_{ol}<V_{il}$ così si legge "0" anche a più di rumore.

Leggere "1" con una porta logica equivale
- ad applicare una tensione tra $V_{ih}$ e $V_p$ 
- a scambiare una corrente tra 0-$I_{ih}$. 
L’uscita precedente deve essere un buon “1” quindi $V_{oh}>V_{ih}$ così che si legga "1" anche a meno di rumore.

*SUNTINO*
$V_{ih}<V_{oh}<V_{p}$
$GND < V_{ol} < V_{il}$

=> l'intervallo di codifica dello "0" e dell'"1" è più stretto in uscita che in entrata. Perchè fa conto del rumore.


Range di codifica:
![[Pasted image 20231101143548.png]]

### Informazione: tensione o corrente?

#### Codifica in Tensione
Nel caso RTL e tanti altri, la codifica è realizzata tramite livelli di tensione, e si rappresenta il range come illustrato nel paragrafo precedente [[Codifica Binaria#Significato dei livelli di tensione range]].

*Attenzione*: la codifica in tensione non è ottimale! 
Non è in grado di supportare una distanza che si avvicini e superi i 10m, perchè la grandezza di potenziale elettrico dipende dalle sorgenti di carica = la tensione cade e si disperde + il cavo ha anche resistenza caratteristica.

Inoltre se un cavo si danneggia/viene tagliato osservo $V=0$ che è comunque un input valido ed i dispositivi *non si accorgono del guasto*.

#### Codifica in Corrente
Cosa cambierebbe?
La convenzione funziona così:
- CORRENTE IN: *"1"*
- CORRENTE OUT: *"0"*
- NO CORRENTE: *guasto*

"Il mancato scambio di corrente si chiama *configurazione a vuoto*. Significa che non ci sono correnti in uscita da un dispositivo"
L'introduzione di questo terzo stato permette una funzionalità e un'elasticità in più rispetto alla codificain tensione.

