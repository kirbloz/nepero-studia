Richiamo al concetto di onda (armonica)
![[Pasted image 20240106161306.png]]
$$x(t)=A \cos (\omega t + \theta)$$
Con periodo $T=\frac{2\pi}{\omega}$ e $\omega = 2\pi f$ 

Non ci interessano le frequenze tipiche a parte per il fatto che vogliamo rimanere nella condizione di parametri concentrati cioè $l<<\lambda$

---

**DEF** : 
 si definisce $\overline X=Ae^{j\theta}$ fasore associato alla sinusoide a pulsazione $\omega$ il numero complesso tale che$$x(t) = \Re [\overline X e^{j\omega t}]$$
  - Ogni sinusoide è rappresentata da due numeri reali: *ampiezza* A e *fase* $\theta$
  - La frequenza è sempre fissata, sottointesa nel dominio dei fasori
  ![[Pasted image 20240106161822.png]]
  ![[Pasted image 20240106161828.png]]
C'è una corrispondenza biunivoca tra sinusoidi isofrequenziali e fasori

![[Pasted image 20240106162714.png]]
In ogni istante proietto il fasore sull'asse $\Re$ 

## Differenza di fase
La fase $\theta$ rappresenta la traslazione temporale rispetto alla cosinusoide a fase nulla. La differenza di fase $\phi$ tuttavia rappresenta la differenza tra due cosinusoidi (che possono essere a fase nulla o meno).
![[Pasted image 20240106163837.png]]![[Pasted image 20240106164116.png]]
La differenza $\phi$ è solitamente $0<\phi\le\pi$.
>La traslazione ha segno negativo con $\theta >0$ e modulo pari a $\theta/\omega$


**DEF** :
 Si dice che y è in *anticipo* su x, e che x è in ritardo su y - quando ogni massimo di y precede nel tempo un massimo di x.

**DEF** :
 Se la $\phi=\pi/2$ allora si dice che le sinusoidi sono *in quadratura*, ogni volta che una sinusoide ha un valore massimo (minimo), l'altra si annulla.

**DEF** :
  Se la $\phi=\pi$ allora si dice che le sinusoidi sono *in opposizione di fase*, ogni volta che una sinusoide ha un valore massimo (minimo), l'altra ha valore minimo (massimo).

![[Pasted image 20240106164408.png]]



## Proprietà

1. **Biunivocità**, nella trasformazione fasore $\leftrightarrow$ segnale. Vedi prima.

2. **Linearità** (omogeneità + additività)
	DEF : *omogeneità*, una sinusoide moltiplicata per una costante reale $k$ ha come fasore quello di partenza moltiplicato per $k$.
![[Pasted image 20240106164644.png]]
	La somma di sinusoidi isofrequenziali è una sinusoide alla stessa frequenza, con fasore pari alla somma dei rispettivi fasori.
![[Pasted image 20240106164715.png]]

3. **Derivazione**, la derivata di una sinusoide a pulsazione $\omega$ con fasore $X$ è una sinusoide alla stessa frequenza e fasore $j\omega X$ 
![[Pasted image 20240106164929.png]]
	La derivazione implica la rotazione di 90 gradi in senso antiorario del fasore di partenza, e moltiplicazione per $\omega$ del modulo
	$\Rightarrow$ bellissima proprietà per cui le relazioni differenziali nel tempo, sono algebriche in questo dominio!