### Il modello
(sempre in termini statici)
Il *modello logico* a funzione F è rappresentabile così:
![[Pasted image 20231101105102.png]]

Il *modello elettrico* per l'elettronica digitale invece è più articolato:
![[Pasted image 20231101105227.png]]

Il modello elettrico con gli stadi IO descritti a livello *circuitale* ha maggior dettaglio:
![[Pasted image 20231101105442.png]]
*Commento*: Questo modello è bello perchè è descritto matematicamente da *quattro equazioni*, facilmente ricavabili, in funzione delle tensioni e correnti (livello alto e basso).
Purtroppo come abbiamo visto, le porte NOT a interruttori simmetrici realizzate così non hanno livelli 100% forti, ma che sono indeboliti dalla corrente nelle resistenze.
>Comunque gli interruttori sono complementari, quindi posso permettermi di usare delle resistenze "piccole"

*Nota*: gli interruttori così realizzati sono delle porte NOT, per cui è necessario negare anche la funzione logica interna, per ottenere un'uscita F(In)!
### Caratteristiche
Studiamone il comportamento in funzione dell'ingresso.

#### IN = "0"
**STADIO IN** :
Il primo interruttore è chiuso, il secondo aperto. La corrente erogata da $+V_{p}$ scorre in $R_{ip}$ e la chiamo $I_{il}$ perchè corrisponde a "low-in", ingresso basso. La chiamo V_IL perchè "low-in"
L'entrata della funzione logica (uscita stadio IN) sarà:
$$\large V_{in} \equiv V_{il}= V_{p}-R_{ip}\cdot I_{il}$$
=> E' un "1" indebolito.
>Mi piacerebbe una $R_{ip}$ più piccola possibile

**STADIO OUT** : 
Il comando sugli interruttori dello stadio di uscita sarà NOT($V_{il}$) dunque uno "0".
Il primo interruttore è chiuso ed il secondo è aperto. 
La corrente generata da $V_{p}$ ha un percorso valido  attraverso $R_{op}$, verso OUT, nel carico successivo.
L'uscita dello stadio OUT (uscita del dispositivo) sarà:
$$\large V_{out} \equiv V_{oh}= V_{p}-R_{op}\cdot I_{oh}$$
=> OUT=~~F("0")~~ ma è un "1" indebolito
>Mi piacerebbe una $R_{og}$ più grande possibile ~~non sono sicuro di un cazzo~~

#### IN = "1"

**STADIO IN** :
Il primo interruttore è aperto, il secondo è chiuso. La corrente generata da $+V_p$ non ha percorso verso massa sullo stadio IN, per cui andrà a scorrere nello stadio OUT.
Nell'entrata della funzione logica si leggerà una tensione dovuta alla corrente di carico del dispositivo precedente a questo, la chiamiamo $I_{ih}$ perchè è "high-in", in ingresso quando comando alto.
L'uscita dello stadio IN sarà:
$$\large V_{in} \equiv V_{ih} = I_{ih}\cdot R_{ig} $$
=> E' uno "0" indebolito
>Mi piacerebbe una $R_{ig}$ più piccola possibile

**STADIO OUT** : 
Il comando sugli interruttori dello stadio di uscita sarà NOT($V_{ih}$) dunque un "1".
Il primo interruttore si apre ed il secondo si chiude. 
Per questo la corrente generata da $V_{p}$ non ha un percorso valido; dunque la corrente che attraversa l'interruttore sarà quella di carico $I_{ol}$ che chiamo I_OL perchè è la corrente OUT data da un livello IN LOW.
L'uscita dello stadio OUT (uscita del dispositivo) sarà:
$$\large V_{out} \equiv V_{oh}= R_{og}\cdot I_{ol}$$
=> OUT=~~F("1")~~ ma è un "0" indebolito

*ALTRE COSE CERTE*

$I_{oh}\geq I_{ih}$           perchè potrebbero esserci correnti interne da altri dispositivi.
$I_{ol} \geq I_{il}$            per lo stesso motivo.

Per il rumore sulla tensione:
$V_{ih}=V_{oh}\pm 100 \text{mV}$ 
$V_{il}=V_{ol}\pm 100 \text{mV}$

>Siccome però ci piace parlare in termini di "estremi", se V_ih è il minimo valore che in ingresso si interpreta come "1", allora sarà PIU' PICCOLO di V_oh, il massimo valore che il dispositivo trasmette come "1" (perchè non esiste la situazione di rumore nullo)
- La codifica in entrata viene fatta su valori con range maggiori che in uscita

$V_{ih}<V_{oh}$ e $V_{il}>V_{ol}$


![[Pasted image 20231101162849.png]]