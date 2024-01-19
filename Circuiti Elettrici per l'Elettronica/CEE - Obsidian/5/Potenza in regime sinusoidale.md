In regime sinusoidale bisogna fare un discorso apposito per la potenza: il concetto di potenza media non basta (e quella istantanea oscilla!) per caratterizzare i fenomeni energetici in alternata. 
Andremo a definire la potenza reattiva, apparente e fattore di potenza, che sono delle grandezze semplici ma efficaci.

## Intro

Prendo bipolo con rif associati
![[Pasted image 20240108151125.png]]
so che la potenza *istantanea* assorbita è $p_{a}(t)=v(t)\cdot i(t)$ e questa vale SEMPRE.
Ma vogliamo una trattazione SPECIALE IN REGIME SINUSOIDALE.

A regime con pulsazione $\omega$ osservo:
![[Pasted image 20240108151233.png]]
![[Pasted image 20240108151239.png]]
Usando la formula generale nota:
![[Pasted image 20240108151259.png]]
Non mi dice molto questa sbrodolata.
$p(t)$ oscilla a frequenza doppia, e ha valor medio diverso da zero.

Proprietà trigonometrica utile:
![[Pasted image 20240108151513.png]]


## Potenza istantanea

**DEF** : 
 in regime sinusoidale il calcolo della *potenza istantanea* restituisce questo aborto.![[Pasted image 20240108152144.png]]
Il termine blu è costante, il secondo termine oscilla a pulsazione doppia $2\omega$. 

![[Pasted image 20240108151926.png]]

### Potenza attiva

**DEF**:
 chiamo *potenza attiva* $P$ il termine costante di $p(t)$ e lo chiamo $$P = \frac{1}{2}\,\, V_{m}\, I_{m}\, \cos(\theta_{v}- \theta_i)$$
 Si misura in Watt. Coincide con la potenza media su un periodo della potenza istantanea. A volte la si chiama proprio potenza media.

- La potenza *attiva* può assumere valori positivi o negativi. E' pari al valore medio meno un pezzettino piccolino dato da quel coseno lì del cazzo.
- Il segno della potenza *attiva* è dettato dal $\cos(\phi)$ dunque la differenza di fase non solo indica la sfasatura di corrente e tensione, ma determina anche il segno del valore medio di potenza assorbita da un bipolo $\Rightarrow$ <span style="background:#b1ffff">permette di classificare i bipoli in base alla passività</span>
- La *potenza istantanea* $p(t)$ oscilla attorno al suo valore medio $P$, la *potenza attiva*, con una ampiezza di oscillazione $\frac{1}{2}V_{m}I_{m}$
- L'<span style="background:#b1ffff">energia assorbita</span> su tempi $\Delta t$ più lunghi del periodo $T$ sono influenzati da questo valore medio. Utilissimo!
![[Pasted image 20240108152743.png]]
>posso approssimare alla media perchè delta t >>> T
### Potenza di picco

**DEF** :
 definiamo la potenza di *picco* (o picco-picco) come il *massimo della potenza istantanea* e dunque vale tutto il suo valore medio sommato al massimo del termine oscillante (coseno = 1) $$P_{picco}=P + \frac{1}{2}V_{m}\,I_{m}$$
### Potenza assorbita dai componenti

#### Resistore
 $\overline V = R \overline I$
Corrente e tensione in fase: $\quad \phi=0\quad \theta_v=\theta_i$
Le ampiezze: $\quad V_{m}=R\,I_{m}$

Potenza istantanea:
![[Pasted image 20240108153854.png]]

Potenza media:
![[Pasted image 20240108153958.png]]

Note:
- Ampiezza = al valore medio
- Picco uguale al doppio della potenza media
- Potenza istantanea sempre NON NEGATIVA (componente passivo)

#### Induttore
$\overline V = j\omega L \overline I$
La corrente è in anticipo: $\quad\phi = \frac{\pi}{2}\quad \theta_v=\theta_{i}+ \frac{\pi}{2}$
Le ampiezze: $\quad V_{m}=\omega L I_{m}$

Potenza istantanea:
![[Pasted image 20240108154641.png]]

Potenza media:
$$P= \frac{1}{2}\omega L I_{m}^{2}\,\cos\left( \frac{\pi}{2}\right) = 0$$
Note:
- la potenza media è nulla => è un elemento che su un periodo non assorbe nè genera! Durante $T/4$ assorbe $w$ e nel successivo $T/4$ restituisce $w$

#### Condensatore
$\overline V = \frac{1}{j\omega C} \overline I$
La corrente è in anticipo: $\quad\phi =- \frac{\pi}{2}\quad \theta_i=\theta_{v}+ \frac{\pi}{2}$
Le ampiezze: $I_{m}= \omega C V_{m}$

Potenza istantanea:
![[Pasted image 20240108155435.png]]

Potenza media:
$$P= \frac{1}{2}\omega C\, V_{m}^{2}\,\cos\left( -\frac{\pi}{2}\right) = 0$$
Note:
- la potenza media è nulla => è un elemento che su un periodo non assorbe nè genera! Durante $T/4$ assorbe $w$ e nel successivo $T/4$ restituisce $w$

>Se sono in fase, p(t) non cambia mai segno.
>Altrimenti se sono in quadratura cambia segno periodicamente.
## Valore efficace
Assumiamo in ipotesi un segnale periodico.

**DEF** :
 chiamo *valore efficace* il valore quadratico medio di una grandezza circuitale che ci interessa. Nel caso specifico del regime sinusoidale osserviamo:
 ![[Pasted image 20240108155705.png]]![[Pasted image 20240108155712.png]]


MA QUINDI PERCHE' STUDIO LA POTENZA ATTIVA/MEDIA?
PERCHE' MI PERMETTE DI CALCOLARE L'ENERGIA ASSORBITA SI.. MA ANCHE!

Si osserva che il *valore efficace della potenza media* in regime sinusoidale vale $$P_{eff}= V_{eff}\, I_{eff}\, \cos\left(\theta_v-\theta_{i}\right) $$

>Per il resistore si osserva
>![[Pasted image 20240108155846.png]]
>La potenza media efficace del resistore è il valore della corrente *costante* che induce nel resistore la STESSA potenza media che si avrebbe in alternata.

**Questa grandrezza è estremamente utile perchè permette di capire come trasmettere in regime AC la stessa potenza DC**



Da qui puoi vedere [[Potenza Complessa]]
