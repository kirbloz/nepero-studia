## Reminder tecnologia BJT:

### Modello circuitale
La *JE* si comporta come un diodo, la *JC* come un generatore di corrente. 
Preferiamo il modello con le RES.
![[Pasted image 20231101175432.png]]    ![[Pasted image 20231101175637.png]]

### Comportamento
Un comportamento approssimato è:![[Pasted image 20231101175908.png]]

<span style="background:#b1ffff">INTERDIZIONE</span>     $V_{be}<V_{s}$      $I_{c}<I_{cbo}$ 
<span style="background:#d4b106">ZONA ATTIVA </span>     $V_{be} \sim V_{s}$      $I_{c}=\beta \cdot I_{b}$
<span style="background:#fdbfff">SATURAZIONE</span>     $V_{be}>V_{s}$      $I_{c}<\beta \cdot I_{b}$

Per l'interruttore (uso che ne facciamo noi per le logiche) ci interessa solo l'interdizione e la saturazione, perchè rappresentano interruttore aperto e interruttore chiuso rispettivamente.

## Modello interruttore digitale BJT
![[Pasted image 20231101180508.png]]
Boh mai visto sto coso. Che schifo.
### Comportamento dinamico
Comunque sia.. 
Questo modello (^) mi fa vedere bene il concetto di cariche intrappolate nella base => *ritardo in ingresso*.
![[Pasted image 20231101175637.png]]
> Commutazioni:
> Da 0 a 1: poco ritardo, la base si riempie subito e subito scorre $I_{c}$ di saturazione
> Da 1 a 0: tanto ritardo, la base è lenta a svuotarsi!

# RTL
Prime famiglie logiche bipolari, utilizzate per le prime 
esperienze di elettronica digitale su silicio. 
![[Pasted image 20231101182041.png]]

- La porta NOT richiede l'integrazione di due resistenze (porta simmetrica)

**Modello statico**
- Lavora tra interdizione (spento) e saturazione. La saturazione ha queste caratteristiche:
       $I_{c}< I_{b}\cdot \beta$
       $I_{b}=(V_{in}-V_{be\text{ ,sat}}) \cdot 1/R_{b}$
       $I_{c}= V_{cc}-V_{be\text{ ,sat}}) \cdot 1/R_{c}$

**Fan-Out**
- La corrente in uscita deve "soddisfare i requisiti" di corrente in entrata. Analizziamo l'output di corrente nei due casi:

$V_{A} = V_{out}=$"1", quindi NOT("0") => *INTERDIZIONE*
$$\frac{V_{cc}-V_{out}}{R_{c}}= N\cdot \frac{V_{in}-V_{be\text{ ,sat}}}{R_{b}}$$

$V_{A} = V_{out}=$"0", quindi NOT("1") => *SATURAZIONE*
$$\frac{V_{cc}-V_{out}}{R_{c}} + N\cdot I_{il}< I_{c \text{,max}}$$

**Modello dinamico**
- La capacità di carico si scarica velocemente sul transistore in conduzione con Rc (resistenza in saturazione è piccola)
- La capacità di carico però si carica lentamente su Rc, che equivale a una RES molto grande (ritardo IN)

**Consumo**
- I dispositivi RTL dissipano potenza statica quando $V_{out}=$"0" perchè la corrente di alimentazione a livelli bassi è considerevole - $I_{cc,l} > I_{cc,h}$.

## Debolezze
RTL non dura a lungo, viene quasi subito sostituito da DTL.
Il problema è che con "0" in uscita va tutto bene, la $I_{ol}$ è OK, ma con "1" ho bisogno di una corrente che piloti ""abbastanza"" tanti carichi: "1" dipende da $I_{oh}$ per cui è debole!
=> Esiste una $I_{ih}$ per cui serve $I_{oh}$ bella piena. 
<span style="background:#fff88f">I CARICHI SCAMBIANO CORRENTE SU OUT="1"</span>

---
## Analisi a vuoto
Il mattoncino elementare della RTL è la porta NOT.
L'analisi a vuoto è quella che mi dice se un dispositivo ha comportamento rigenerativo.
Vedi [[Immunità al rumore]].

Supponiamo a vuoto dunque non collego l'uscita a nulla:
       $I_{ol}=I_{oh}=0$
Ma
       $I_{oh}=0 \Leftrightarrow V_{oh}=V_{cc}$
Quindi la tensione IN = tensione OUT.
Queste sono le *ipotesi*.
![[Pasted image 20231101212632.png]]

Uscita alta:
$V_{oh} = V_{cc}$
	// BJT spento, la corrente non passa in Rc
Entrata bassa:
$I_{il}=0$ 
	Se applico uno "0" tensione IN allora non c'è corrente IN, o è trascurabile.

Uscita bassa:
$V_{il}$ =0.5V 
	Soglia per cui scorrono correnti trascurabili
$V_{ol}= 0.3V$
	BJT in saturazione outputta la saturazione di Vce
Entrata alta:
$V_{ih}$ = 0.7V 
	Soglia di accensione (minimo valore per avere "1" -> saturazione)
$I_{ih} =(V_i -0.7V) / R_{b}$
	Con un ingresso alto c'è corrente in base che fa cadere la tensione di ingresso su Rb


*Commento*: da questi dati il range di codifica delle RTL è tutto stupido: è schiacciato verso GND.
	![[Pasted image 20231101213412.png]]

$V_{ol} < V_{il}$ indica che il range di codifica in ingresso è più "largo" di quello in uscita, quindi considera il rumore.
=> RTL è *rigenerativa*. Ha immunità al rumore sulle tensioni.
>$\vert V_{ih}-0.7 \vert > \pm 100mV$ è un ottimo test perchè 0.7 è necessario ad attivare il BJT, e se il "rimasuglio" è superiore al rumore allora ez, non sminchia

E sulle correnti? Voglio definire $I_{ih}$ (minimo valore IN per leggere "1")
$$I_{ih}= \frac{V_{in}-0.7V}{R_{b}}$$
Perchè mi interessa? Perchè nell'analisi a vuoto è l'unica corrente che non sta a zero!

## Analisi in pilotaggio
Il mattoncino elementare della RTL è la porta NOT.
L'analisi non a vuoto (l'ho chiamata in pilotaggio perchè mi sembrava fico) è quella che mi aiuta a capire il fan-out.
Vedi [[Fan-Out Statico]].

![[Pasted image 20231101215833.png]]

