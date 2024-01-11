Sono logiche a livelli attivi. Cosa vuol dire attivi? 
Immagina di scrivere in una memoria: avrà due segnali, W-write e R-read. Alla memoria bisogna dire "dato" - "comando" - "indirizzo a cui accedere". Una uscita attiva alta è a 1 quando voglio W, a 0 quando voglio NOT -W. Attiva bassa quando con "0" voglio W-scrivere; "1" non voglio scrivere, NOT-W.

---

<span style="background:#b1ffff">Si parte con questa roba perchè gli interruttori BJT partono con un "1" forte ed uno "0" debole. </span>

---
**USCITA DIGITALE FORTE**: <span style="background:#fff88f">si dice che un'uscita digitale (codificata in binario) è "forte" se la tensione di uscita varia *poco* al variare di</span> $I_{out}$ <span style="background:#fff88f">- corrente del carico</span>.
Dunque un'uscita in tensione è forte se il componente riesce a mantenere il suo segnale in uscita indipendentemente dalla corrente erogata, sia che gli chiedo 1mA che 100mA.

>E' debole se invece la corrente che esce dipende dalla resistenza R e pilota anche V.

Per rendere un'uscita forte si fa uso delle resistenze, le si piazza in punti particolari a seconda dell'effetto che si vuole ottenere.
E' una logica che permette di avere OUT = IN.
Le due configurazioni differiscono per "forza" dei livelli. Analizziamole.
>Si codifica l'informazione nell'azione di chiudere/aprire un interruttore. Dunque il segnale è codificato in tensione.

---
#### Funzione identità
![[Pasted image 20231030171820.png]]![[Pasted image 20231030174447.png]]![[Pasted image 20231031151753.png]]

1 - *A)* Al momento zero abbiamo IN="0". 
Quando si ha IN="0", l'interruttore è aperto e non scorre corrente da $V+$, quindi OUT="0"?

CARICO: L'uscita del transistor è su di una resistenza collegata al GND (per non fare CC); il carico rappresenta però un generatore di tensione, quindi esisterà una corrente che attraversa l'uscita.
=> Sull'uscita si legge la corrente dovuta al partitore rappresentato dalle impedenze di carico e dall'impedenza della R a GND.

Quando IN="0", OUT = $GND + i_{residua}$
<span style="background:#fff88f">=>"0" debole.</span>

2 - *B)* Al momento zero abbiamo IN="1". 
Quando si ha IN="1" l'interruttore si chiude ed inizia a scorrere corrente dal generatore verso GND, attraversando la R e poi verso il carico. La tensione non dipende dalla corrente.

Quando IN="1", OUT = $+V$ 
<span style="background:#fff88f">=>"1" forte</span>

---
I BJT per costruzione e per utilizzo iniziale erano proprio così, con E collegato al circuito, B al comando e C al GND, o il riferimento equivalente. Dunque BJT -> porta NOT.
#### Funzione NOT
![[Pasted image 20231030174828.png]]![[Pasted image 20231030174841.png]]![[Pasted image 20231031151812.png]]

E' una logica  "1" debole e "0" forte, ~~perchè in serie all'uscita è collegata una resistenza~~. Analizziamo la configurazione.

3 - *B)* Al momento zero abbiamo IN="1". 
Quando si ha IN="1", l'interruttore è chiuso quindi si crea un passaggio verso GND: viene favorito dalla corrente che eviterà la strada out->carico e la tensione "cadrà tutta prima". Dunque sul nodo in uscita si leggerà una tensione GND => OUT="0", bellissimo perchè è GND

CARICO: L'uscita del transistor è collegata al GND (per non fare CC c'è una resistenza in ingresso);

4 - *A)* Al momento zero abbiamo IN="0". 
Quando si ha IN="0", l'interruttore è aperto e non c'è più un percorso per la corrente da $V+$ a GND.
La corrente è costretta a passare attraverso out, dentro il carico e finire nel GND del carico (prima o poi).
Dunque la tensione che leggiamo in uscita è $+V$ MENO la caduta sulla resistenza in entrata.
=> OUT="1" ma $V_{out}=+V-R_{in}*I_{in}$ 
"1" debole


