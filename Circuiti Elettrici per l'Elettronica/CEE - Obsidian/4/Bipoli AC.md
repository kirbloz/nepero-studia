Dal teorema di Thevenin un generico bipolo ha: $\quad V=Z_{T}I+V_T$
<span style="background:#fff88f">In assenza di generatori indipendenti</span>, la relazione tra $V$ e $I$ è lineare (perchè a circuito aperto non ci sarebbe tensione $V_T$)
![[Pasted image 20240107190943.png]]

Dall'esterno? Perchè?
Perchè applico Thevenin e calcolo l'impedenza totale. A quel punto posso classificare il comportamento del bipolo [[Bipoli AC#Classificazione]] e capire se è resistivo, induttivo, capacitivo e "quanto" lo è.

## Impedenza
Estendo il concetto di impedenza. Si può applicare non solo a un singolo bipolo, ma a connessioni di elementi sia resistivi, dinamici che generatori
**DEF** :
 Per un generico bipolo senza generatori indipendenti, l'impedenza del bipolo è il rapporto tra il fasore della tensione $V$ ed il fasore della corrente $I$
 $$\large Z=\frac{V}{I}=\frac{V_{m}e^j\theta_v}{I_{m}e^{j\theta_{i}}}=\frac{V_m}{I_m}e^j(\theta_v-\theta_i)$$
 Si dice che *$Z$ caratterizza completamente il bipolo in regime sinusoidale*
Inoltre in generale si esprime come:
$$Z=R+jX$$
Dove $R\in\Re$ è la parte reale - *resistenza* - e $X\in\Im$ è la parte immaginaria - *reattanza*.
- **Modulo** dell'impedenza: rapporto fra l'ampiezza di tensione e corrente
- **Argomento** dell'impedenza:differenza di fase tra la tensione la corrente
![[Pasted image 20240107191413.png]]
![[Pasted image 20240107191234.png]]



### Classificazione
![[Pasted image 20240107195201.png]]
Definiamo la fase dell'impedenza come la differenza di fase della tensione e della corrente. $$\large \phi_Z = \theta_v-\theta_{i}= \arctan(\frac{X}{R})$$
Dunque possiamo classificare i bipoli in base allo sfasamento tra tensione e corrente che la loro impedenza impone.

---
- Un generico bipolo è *resistivo* (passivo) se la sua reattanza $X$ è nulla
**Resistore**
	$Z = R$ 
	$X=0$

La $\arctan(X/R)$ sarà nulla, quindi per i bipoli resistivi, tensione e corrente sono in fase.

---
- Un generico bipolo è *reattivo* (puro) se la sua resistenza $R$ è nulla
>Noi comunque assumiamo in ipotesi di avere a che fare con un bipolo passivo per cui $R>0$ e la fase al max $\pi/2$
>Se dovessi comunque pensare a $R=0$ otterrei $\arctan\frac{X}{R}\rightarrow \infty$ quindi $\phi = \pm \pi/2$

**Induttore**
	$Z = j\omega L$ 
	$X=\omega L > 0$

Un generico bipolo è *induttivo* se la sua reattanza $X$ è positiva
Calcolo  un $\phi = \arctan(X/R)$ che risulta essere $0<\phi<\pi/2$; nel primo quadrante.
Con $\theta_v-\theta_{i}>0$ la corrente sarà in ritardo.

**Condensatore**
	$Z = -j/(\omega C)$ 
	$X=-1/(\omega C) < 0$

Un generico bipolo è *capacitivo* se la sua reattanza $X$ è negativa
Calcolo  un $\phi = \arctan(X/R)$ che risulta essere $-\pi/2<\phi<0$; nel quarto quadrante.
Con $\theta_v-\theta_{i}<0$ la corrente sarà in anticipo.

![[Pasted image 20240109001149.png]]
### Ammettenza
![[Pasted image 20240107201352.png]]

in AC G != 1/R in generale
mentre sempre Y=1/Z

