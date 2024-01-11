Ripassone a inizio SED:

![[Pasted image 20231110152839.png]]
![[Pasted image 20231110152853.png]]
Stadio ingresso + Stadio funzionale + Stadio uscita
Un dispositivo ne pilota altri, interfacciamento = collegamento tra uno o più dispositivi.
Vorrei che indipendentemente da cosa piloto, la corrente sia uguale e sufficiente (di solito vale dentro le famiglie logiche)

$I_{ol} \rightarrow$ corrente che entra nel dispositivo pilota quando questo impone uno "0" 
$I_{il} \rightarrow$ corrente che esce dal dispositivo pilotato quando il dispositivo pilotato riceve "0"
$I_{oh} \rightarrow$ corrente che l'uscita eroga quando impone "1"
$I_{ih}\rightarrow$ corrente che il dispositivo assorbe quando riceve "1" 

#### Uscite imposte
Per *segnali a “1”* l’uscita impone una tensione
$V_{o}\equiv V_{oh} = V_{p}- R_{op}\cdot I_{oh}$
- se $I_{oh}\sim 0$ –uscita a vuoto- allora $V_{oh} \sim V_p$, 
- se $I_{oh}=I_{oh\text{, max}}$ allora $V_{oh}=V_{oh\text{, min}}$

$I_{oh\text{, max}}$ dipende dall’interruttore;
$I_{oh\text{, max}}=N_{max}\cdot I_{ih}$ 


Per *segnali a “0”* l’uscita impone una tensione 
$V_{o}\equiv V_{ol} = R_{og}\cdot I_{ol}$
- se $I_{ol}\sim 0$ –uscita a vuoto- allora $V_{ol} \sim GND$, 
- se $I_{ol}=I_{ol\text{, max}}$ allora $V_{ol}=V_{ol\text{, max}}$

$I_{ol\text{, max}}$ dipende dall’interruttore;
$I_{ol\text{, max}}=N_{max}\cdot I_{il}$ 


$V_{ol}$ e $V_{oh}$ legate all'uscita del dispositivo
$V_{il}$ e $V_{ih}$ legate all'entrata del dispositivo

ROP e ROG -> dev'essere piccola!
I_OH non la voglio dover babysittare troppo perchè influisce sul fan out e non so quanti dispositivi voglio connetterci!

#### Relazioni
Equazioni:
$V_{ih}=I_{ih}\cdot R_{ig}$
$V_{ol} = I_{ol}\cdot R_{og}$ 
$V_{oh} = V_{p}- R_{op}\cdot I_{oh}$
$V_{il} = V_{p}-R_{ip}\cdot I_{il}$

Per i *segnali a "1"*:
$V_{oh,\,min}<V_{o}<V_{p}$ con $V_{oh,\,min}= V_{p}-R_{op}\cdot I_{oh,\,max}$

Per i *segnali a "0"*:
$GND < V_{o} < V_{ol,\,max}$ con $V_{ol,max}=R_{og}\cdot I_{ol,\,max}$

Quando V_s è la soglia in ingresso tra "0" e "1".
$$\large \Rightarrow V_{ol,\,max}<V_{il,\,max}<V_{S}<V_{ih,\,min}<V_{oh,\,min}$$

#### Rumore Tensione
Per effetto del rumore le soglie sono calcolate così:
$V_{il,\,max}=V_{ol, max}+V_{n}$
$V_{ih,\,min}=V_{oh,\,min}-V_{n}$


#### Livelli di corrente 
![[Pasted image 20231110160443.png]]

#### Livelli di tensione
ENTRATA
Applicare uno <span style="background:#b1ffff">“0”</span> (<span style="background:#affad1">“1”</span>) in ingresso ad una porta logica equivale ad applicare una <span style="background:#b1ffff">tensione tra Gnd e Vil</span> (<span style="background:#affad1">tra Vih e Vcc</span>) e a scambiare una <span style="background:#b1ffff">corrente tra 0 e Iil </span>(<span style="background:#affad1">Iih</span>)

USCITA
Uno “0” (“1”) generato da una porta logica equivale ad una
tensione tra Gnd e Vol (tra Voh e Vcc) e a scambiare una corrente
tra 0 e Iol (Ioh)

---

*Interfacciamento in tensione*: vil voh abbiamo due valori "principe", che sarebbero $V_{il}$ (massimo valore che viene codificato come "0" in ingresso) e $V_{oh}$ (minimo valore che viene codificato come "1" in uscita)
>1 massimo è alimentaione, 0 minimo è GND

*Tensione di soglia* VIl-Vih, V_il < V_ih e ho del rumore
Potrei avere $v_{oh}< V_{nh}$

#### Parametri Statici
**FAN OUT**: 
Numero massimo di carichi, con uscita "0" e "1", pilotabili dal dispositivo
 $N_{max}=min\{\frac{I_{oh}}{I_{ih}},\,\frac{I_{ol}}{I_{il}}\}$
 Di solito è almeno 10.

**Immunità al rumore**:
Massimo rumore che può essere sommato/sottratto all'uscita
$V_{n}=min\{V_{il}-V_{ol}; V_{oh}-V_{ih}\}$

**Dissipazione di potenza statica**:
Parametro statico legato all'alimentazione $P=V_{p}\cdot I_{p}$
- INGRESSO:
	$I_{il}\,\,I_{ih}\,\,$ e le correnti di perdita
- FUNZIONALE:
	Bassa dissipazione di potenza statica
- USCITA:
	$I_{ol}\,\,I_{oh}$ e le correnti di perdita

Lo stadio simmetrico non ha percorso diretto tra alimentazione e massa quindi $I_{p}\sim 0$, correnti di perdita dovute ai minoritari
>CMOS: ha Iih e Iil di gate, quindi consuma pochissimo!!

Correnti IN = Correnti OUT, piccole ma mai nulle, servono comunque a trasportare informazione




