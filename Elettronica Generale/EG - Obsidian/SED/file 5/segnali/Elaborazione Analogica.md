## Adattare i segnali analogici al dispositivo
Il primo pezzo di elaborazione che si fa ad un segnale analogico nudo e crudo sta in questo stadio..
![[Pasted image 20231209155620.png]]
Stadio di **condizionamento** tipico:
- Eventuale stadio a *guadagno* G 
$$e’(t) = G_1 \cdot e(t)+ G_0$$
- *filtro* passa-basso (o passa-banda) con frequenza di taglio $f_{ch} < f_{s}/2$ e ordine $m$

---

Possibili **problemi**:
- Il filtro, di ordine limitato, non attenua sufficientemente oltre $f_s/2$
- $G$ non è costante in tutta la banda di interesse (OA, filtro)
- $v(t)$ risulta in ritardo rispetto a $e(t)$, ritardo di propagazione

Possibili **soluzioni**:
- Sovracampionamento rispetto alla banda utile del segnale
![[Pasted image 20231209112144.png]]
Ovviamente diventa un meccanismo più costoso
![[Pasted image 20231209155655.png]]


## Convertitore AD
Lo stadio di **conversione** è caratterizzato da 3 parametri:
1. *Frequenza di campionamento* $f_{s}$ (Tempo di conversione Ts = 1/fs)
2. Numero $B$ di *bit* del convertitore
3.  *Stabilità delle tensioni di riferimento* $V_{refh}$, $V_{refl}$

Da questi parametri si ricava la <span style="background:#fff88f">legge di conversione</span> 
$$x=2^B(v-V_{refl})/(V_{refh}-V_{refl})$$
- ove $x$ è il valore convertito in digitale
- e $v$ è il valore della tensione in lettura

---
### Tempo
>Sta cosa qui non l'ho capita

C'è un certo grado di "incertezza", perchè i valori di tensione e tempo sono in realtà range.
$$\{\, x \pm\Delta x,\, t\pm \Delta t\,\}$$
Si fa una rappresentazione implicita del tempo quando si converte poichè:
$(t_{n}- t_{n-1} = T_{s}= \frac{1}{f_{s}})$ il tempo tra due campionamenti è fisso! E' il periodo relativo alla frequenza di campionamento.
Da cui ricavo anche la relazione tra voltaggio-valore digitale:
$$x(n) = v\,(n\cdot T_s)$$

---
### Rumore
Il rumore associato all’ADC dipende da:
-  tempo di apertura, linearità, $V_{ref}$ ...
- rumore di quantizzazione associato ai $B$ bit 
>Nota: S/H può non essere utile (es. approx. succ.) che cosa è s/h? sample and hold

---


>Boh io riporto le slide ma non credo che questa cosa ce la chieda in questa maniera. Sono da vedere i TE
![[Pasted image 20231209113124.png]]
![[Pasted image 20231209113133.png]]
![[Pasted image 20231209113152.png]]

Quindi il **rumore di quantizzazione**:
![[Pasted image 20231209160614.png]]
Errore di quantizzazione $q_{T}$:
$$q_{T} < \Delta=2^{-B}\,(V_{refh}-V_{refl})= 2^{-B}FS$$
![[Pasted image 20231209160726.png]]

Funzione che descrive il segnale analogico in ingresso:
![[Pasted image 20231209160803.png]]

Da cui, sfruttando la formula di prima - dipendente dai bit di conversione e dalle tensioni di riferimento..
![[Pasted image 20231209160846.png]]

### ENOB
Effective Number Of Bits.
Ci interessa il *numero di bit effettivi* di un convertitore, e questo dipende dalle NON IDEALITA REALIZZATIVE, quali:
- non linearità
- rumore alle tensioni di riferimento
- non linearità di S/H

Dal numero di bit nominali si scende a causa delle non idealità sopra elencate. I bit effettivi dipendono anche dal filtro anti-aliasing.
> Più il filtro filtra, più bit nominali sono circa quelli effettivi.

![[Pasted image 20231210114937.png]]

![[Pasted image 20231210115208.png]]
### Convertitori

- **Tradizionali**
	Sono *convertitori flash* se sfruttati per i sistemi che lavorano ad elevate velocità ($f_{b}> MHz$), si chiamano quindi .
	Si realizzano come un banco di $2^{B}-1$ comparatori che lavorano su soglie differenti.
	Il tempo di conversione diventa quindi $T_{s}=T_{comp}+T_{logic}$

	Sono *convertitori con DA in reazione* se invece si usano per sistemi a bassa velocità ($f_{b}<<MHz$).
	Ad esempio per le approssimazioni successive.
	Il tempo di conversione diventa  $T_{s}=T_{comp}+T_{logic}+T_{assDA}$

- **Modificati**
	Usati nelle approssimazioni successive parallele. 
	Sono più veloci perchè il DA ha un solo bit.
	Con un S/H dopo il $G=2$ si può realizzare un'architettura di convertitori AD modificati collegati come pipeline.
	![[Pasted image 20231209161722.png]]

- **Speciali**
	Sono dei convertitori non lineari (es. VoIP) e la conversione AD è meno precisa.

>Qua ci sarebbe una slide che parla della conversione logaritmica, legge micro, legge A etc etc vabe 

#### Esempio convertitore AD
![[Pasted image 20231210115254.png]]![[Pasted image 20231210154918.png]]

![[Pasted image 20231210154934.png]]

In generale ci serviranno i convertitori a 8 bit. Quindi avrò $2^8$ intervallini possibili, ognuno corrispondente ad un numero.. servono 255 soglie.. 
- Ci sono i **flash converter**, roba HW straveloce si usa per immagini e video processing.
- Ci sono anche i **convertitori ad approssimazioni successive**. ENOB circa 7-9.
  Ma come caccio 255 convertitori in un MCU?
  Sfrutto un approccio seriale, che è un po' più lento di quello parallelo.
Leggi qua sotto..
![[Pasted image 20231210160111.png]]

Dunque per 255 soglie, con questo metodo, basta una sola soglia!

#### Rumore
Immagino di avere alimentazione da 3 V e 300 soglie da realizzare. Dunque ho ogni intervallino che dura 10mV.
$$\frac{3V}{300}=10mV$$
Se arrivassi ad avere 1mV, avrei che il rumore interferisce in maniera significativa sulla conversione. 
Ergo esiste un limite a quanti bit posso convertire alla volta! Circa 10/12bit max.
Oltre questo limite non uso più convertitori integrati del cazzo alla MCU ma uno a parte, esterno, che collego alla SPI.
>Avrò tensioni di conversione più alte
>Non ci sarà il disturbo EM della ALU

### Convertitore AD Sigma/Delta
Dal mondo audio nasce un problema: il segnale audio varia molto lentamente, quindi i convertitori soggetti al problema di aliasing non vanno bene!
Per questo motivo invece di campionare e lavorare sui valori assoluti, si passa ai *convertitori a inseguimento* che convertono le differenze nel tempo.

---


DELTA: Questa variante di convertitore analogico-digitale si basa sul convertire le *differenze nel tempo* al posto del valore assoluto di $v(t)$.
- L'uscita D è una sequenza di bit
- E' un convertitore a inseguimento. A inseguimento finito si ottiene una sequenza 010101.
  Se integro questa sequenza ottengo 0! Perchè la variazione è nulla.
- Più aumento la frequenza di lavoro $Ck$ e più aumenta la risoluzione. 
- La $Ck$ è sempre >> della dinamica di $v(t)$, per il TH di Shannon.
![[Pasted image 20231210161304.png]]

DELTA A INTEGRATORE (SIGMA):
Ha le caratteristiche principali simili a quelle del DELTA, però si implementa più facilmente.
![[Pasted image 20231209162844.png]]

**SIGMA-DELTA**:
>Sono i convertitori che trovo ovunque, sia integrati nei FPGA che esterni da collegare alle MCU. Perchè non li integro anche a loro? Perchè per far funzionare questo circuito ci vuole un clock a basso rumore.. che è incompatibile con quello utilizzato per la ALU.

Se considerando le differenze prima e integrando dopo trovo valore nullo... Allora prima integro e poi prendo i $\Delta$!
![[Pasted image 20231210161354.png]]
![[Pasted image 20231210161404.png]]

Il convertitore differenziale a inseguimento, per assestare il valore di Q (v(t) a bassa dinamica) deve attendere $2^N$ colpi di clock (ove $N$ è la dim. del contatore).
- Uscita Q a $N$ bit dopo $2^N$ colpi di clock
- *Decimazione*: rapporto di riduzione = $2^{N}/N$. 
  In realtà i decimatori sono filtri.

Il sovracampionamento migliora SNRa (filtro anti-alias meno critico) e SNRq (sparpaglio meglio la densità spettrale del rumore di quantizzazione).
- Il rumore di quantizzazione additivo bianco (unif in f) non vale per $v(t)$ perchè è costante, quindi il rumore di quantizzazione è coloratissimo.

Una ulteriore riduzione della densità spettrale di $q_T$ in banda è il *noise shaping*. E' una struttura per separare il segnale (portato in bassa frequenza) dal rumore (alte frequenze), che quindi diventa strafacile da eliminare (basta un filtro passa-basso)
- Eseguita dal convertitore sigma-delta nel dominio delle frequenze
![[Pasted image 20231209163831.png]]

#### Conv AD integrati nei MCU
Come già accennato nei MCU posso integrare convertitori fino a un certo numero di bit (10/12) altrimenti gli intervalli per i vari valori diventano troppo sensibili al rumore (servono alte tensioni).
Inoltre i convertitori più fichi - sigma/delta - sono incompatibili con il circuito del processore poichè vogliono un clock a basso rumore (quello della ALU è terribile perchè fa casino!).

Di solito nei MCU a basso costo ci si mettono i convertitori integrati ad approssimazioni successive.

ESEMPIO: ATmega32u4
- 12 canali multiplexati per la conversione. Si usano uno alla volta ponendo su ogni canale anche un tipo di dato diverso. Converto all'occorrenza e leggo subito dopo quindi è lento.
- 10/8 bit (+/-2LSB Accuracy)
- tempo di conversione a 10 bit da 65us = 13 ADC Clocks @ 200kHz - Arduino limita la funzione di campionamento quando è in modalità STANDARD.
- Amplificazione programmabile (1x, 10x, 40x, 200x) utile per convertire segnali piccoli! Questo si può fare grazie ad un AO non invertente che sta posizionato con delle resistenze variabili: un vero potenziometro digitale!
![[Pasted image 20231210162152.png]]
- Riferimento interno di tensione a 2,56V (oppure riferimento a Vcc)
- Interrupt che stimolano la conversione (End-of-Conversion Interrupt); utile perchè così i comparatori non bloccano la CPU in attesa ma fanno il loro lavoro e poi mandano un interrupt quando finiscono.
- Comparatori analogici (confrontano le tensioni tra 2 pin)
## Convertitori DA

**Architettura a correnti pesate**
Come realizzo queste correnti controllate?
Piazzando delle opportune resistenze, ogni ingresso $V_i$ sarà tamponato in modo da ottenere le relative $I_i$.
Immettendo queste correnti in un Amp. Op. con retroazione negativa, avrò la somma di queste correnti che passa sull'impedenza di retroazione, stabilendo la caduta di tensione $V_{out}$.
![[Pasted image 20231210113100.png]]

![[Pasted image 20231210113047.png]]

**Architettura a resistenza pesate**
Come realizzo le resistenze? Creando una sequenza di resistenze in parallelo più una in serie ai paralleli, che mi permette di avere una sola tensione di riferimento ma tante correnti diverse uscenti dai rami.
![[Pasted image 20231210113559.png]]

La soluzione qui sopra si chiama *a rete $R/2R$*
Quella sotto si chiama PWM
![[Pasted image 20231210113642.png]]

### PWM
Pulse With Modulation.
>Definizione da wikipedia

E' un tipo di modulazione digitale che permette di ottenere una *tensione media variabile* dipendente dal rapporto tra la *durata dell'impulso positivo* e dell'*intero periodo* (duty cycle). Allo stesso modo, è fondamentalmente utilizzato per protocolli di comunicazione in cui l'informazione è codificata sotto forma di durata nel tempo di ciascun impulso.

In alcuni circuiti digitali (spec. con MCU), la tecnica PWM può essere utilizzata, con l'ausilio di un semplice filtro RC, per *trasformare un valore digitale in una corrispondente tensione continua*. La maggior parte dei microcontrollori presenti in commercio, infatti, dispone di uno o più timer in grado di generare onde rettangolari con duty-cycle variabile. Programmando opportunamente il timer, si può variare il duty-cycle dell'onda rettangolare e di conseguenza il valore di tensione che si ottiene all'uscita del filtro RC.

----


#### Conv DA integrati nei MCU