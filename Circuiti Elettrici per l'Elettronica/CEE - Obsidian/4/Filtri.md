<span style="background:#fff88f">I bipoli in regime sinusoidale sono filtri.</span>

*Nota Bene*: I filtri sono utili in regime lineare - cioè quando l'ingresso è la somma di armoniche a frequenze diverse.
In base al tipo di filtro il circuito attenuerà le armoniche con frequenze più alte piuttosto che basse, o viceversa.

---

In *DC* conosciamo il comportamento supponendo di essere in AC ma a regime con $\omega=0$
- induttore $Z=j\omega L = 0$ dunque corto circuito
- condensatore $Y=j\omega C=0$ dunque circuito aperto
Se invece la pulsazione tende a $\infty$, il comportamento di induttore e condensatore si scambia.

UN FILTRO SI COMPORTA IN MODO DIVERSO A PULSAZIONI DIVERSE
- risp in ampiezza
- risp in fase
sono entrambe dipendenti dal valore della pulsazione! vedi [[Risposta in frequenza]]

---

**DEF** : 
 indico con *pulsazione di taglio* $\omega_C$ il valore di $\omega$ per cui la risposta in ampiezza è pari al suo estremo superiore diviso per $\sqrt 2$ .
 E' un po la convenzione per dire: questa è la soglia.
 $$\omega_{C} \quad : \quad |\,H(j\omega_{C})\,|=\frac{\sup |H|\,|X_{in}|}{\sqrt2}$$
Al taglio l'ampiezza è $\frac{1}{\sqrt2}$ mentre la fase è $45°$ 
- questo perchè il filtro ideale TAGLIA il segnale in maniera mooolto precisa, lo squadra

>Nei passa-basso(alto) l'intervallo di frequenze che sta sopra(sotto) quella di taglio, si chiama banda eliminata.



---
## Analisi ispezione visiva 
- Se c'è un elemento dinamico, allora è o passa-alto o passa-basso

- Si studiano i circuiti limiti, il caso DC e a pulsazioni molto elevate. Se c'è un elemento dinamico, è facile sostituirlo con il corrispettivo CA/CC.
	- se la pulsazione $\omega \rightarrow 0$ 
	- se la pulsazione $\omega \rightarrow \infty$ 

### Filtro RC

$H= X_{o}/X_{in}$               $X_{o}=H\cdot X_{in}$

$|H| = \frac{1}{1+j\omega CR}$
$\angle H = -atan(\omega CR)$

1. $\omega \rightarrow 0$ : 
	- $|H| \sim 1$
	- $\angle H \sim -atan(0) = 0$
2. $\omega \rightarrow \infty$  
	- $|H| \sim 0$
	- $\angle H \sim -atan(\infty) = -\pi/2$ 

*Conclusione*: il filtro RC, quando lavora a pulsazioni basse ($\sim$ DC) riporta in uscita il segnale di ingresso $X_{in}$ praticamente inalterato.
Quando lavora a pulsazioni alte invece ha uscita nulla e uno sfasamento di squadratura.
Dunque più il segnale ha pulsazione alta e più viene attenuato e sfasato (in ritardo)
=> <span style="background:#affad1">FILTRO PASSA BASSO</span>

*Taglio*: l'estremo superiore dell'ampiezza è $1$, quindi si cerca $|H| = \frac{1}{\sqrt2}$ 
Per il circuito RC vale che $\omega_{C}=\frac{1}{RC}=\frac{1}{\tau}$
Il filtro ideale sopprime tutte le pulsazioni sopra il taglio:
![[Pasted image 20240111154711.png]]

- Per $\omega < \omega_C$ la tensione sul condensatore è circa quella sul generatore
Al cresce di $\omega$ diminuisce l'ampiezza e aumenta lo sfasamento

#### se prendessi l'uscita del resistore?
1. in continua non c'è corrente perchè condensatore -> CA quindi resistore non percorso da corrente. tensione nulla in uscita

2. a pulsazioni altissime invece condensatore CC -> passa tutto, e l'uscita è pari all'ingresso

*Conclusione*: l'andamento è al contrario, quindi un passa alto. passono inalterate le sinusoidi con pulsazione elavate.
- si mantiene il concetto di pulsazione di taglio

### Filtro RL
![[Pasted image 20240111162059.png]]![[Pasted image 20240111162105.png]]

E' un filtro passa alto!
Con sempre $\omega_{C}=1/\tau$ 


## Regime transitorio
Non lo studiamo perchè assumiamo che tutti i nostri circuiti abbiano $\tau > 0$ dunque siano stabili.

Tuttavia sappiamo anche che $\omega_{C}=1/\tau$ ... cioè la <span style="background:rgba(240, 200, 0, 0.2)">durata del transitorio e la banda del filtro sono inversamente proporzionali</span>.
>Se filtro a banda larga allora transitorio breve. Se filtro a banda stretta allora transitorio luungo. Più tau è piccolo più l'esponenziale si esaurisce velocemente.

---

## Classificazione
![[Pasted image 20240111163456.png]]
![[Pasted image 20240111163506.png]]