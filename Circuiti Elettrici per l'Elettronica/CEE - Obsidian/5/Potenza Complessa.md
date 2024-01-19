## Potenza complessa

**DEF** :
 definisco la potenza *complessa* come la potenza assorbita da un bipolo con versi di riferimento coordinati, il numero complesso tale che $$\overline S = \frac{1}{2}\overline V\,\overline I^{*} \quad \quad \Rightarrow \quad 
  S = \frac{1}{2}V_{m}\,I_{m}$$
 Si misura in volt-ampere.

*Convenzione utilizzatori-generatori*
Con riferimenti associati
![[Pasted image 20240108172104.png]]
Con riferimenti antiassociati
![[Pasted image 20240108172134.png]]

### Potenza apparente

**DEF** :
 la potenza *apparente* è definita come il modulo della potenza complessa$$ S= \frac{1}{2}V_{m}I_{m} = V_{e}I_{e}$$
 - <span style="background:#fff88f">E' la potenza dissipata in DC con v e i uguali ai loro valori efficaci in AC</span>
 Si misura in volt-ampere

### Potenza reattiva
L'argomento della potenza complessa è la differenza di fase tra tensione e corrente $$\phi = \arg(\overline S) = \theta_{v}-\theta_i$$
Il *coseno dell'argomento* $\phi$ è detto **fattore di potenza**
Vedi [[Fattore di Potenza]]
Si può riscrivere la potenza complessa $\overline S$ 
![[Pasted image 20240108165326.png]]

P lo abbiamo già visto, è la potenza media/attiva del bipolo.
![[Pasted image 20240108165455.png]]

**DEF** :
 $Q$ è invece detta *potenza reattiva* ed è la parte immaginaria di $S$.
 Si misura in vol-ampere reattivi (VAR)
 ![[Pasted image 20240108165445.png]]

E' direttamente collegata agli elementi dinamici, quindi a quell'energia che viene immagazzinata e ri-restituita; informazione che non ho quanto lavoro con la potenza istantanea.

---
**Triangolo delle potenze**
S è un numero complesso, rappresentabile con un vettore, lo posso disegnare.
$S$ è il vettore. 
$\phi$ è il fattore di potenza, l'argomento.
$|S|$ è il modulo di $S$, la potenza *apparente*.
$Re(S)=P$ è il suo coseno, la potenza *attiva* (media).
$Im(S)=Q$ è il suo seno, la potenza *reattiva*.
![[Pasted image 20240108173131.png]]
In questo triangolo ho tutte le grandezze utili a studiare la potenza in alternata SENZA passare per la potenza istantanea.

---
## Potenza istantanea e complessa
CENNI COMUNQUE SU QUESTA ROBA EH. COSA MI INTERESSA?
La potenza istantanea si può riscrivere anche così:
![[Pasted image 20240108174031.png]]
Cioè conoscere P e Q non mi permette di vedere solo S potenza complessa ma anche p(t) istantanea. Questa espressiome mi permette di studiare bene cosa sono P e Q

*Primo termine*
tensione e corrente sono in fase.
il termine oscilla attorno a $P$ con ampiezza $P$
è sempre non negativo
nei bipoli resistivi (X=0), il flusso di energia è unidirezionale (o assorbe o genera solo!)
![[Pasted image 20240108180426.png]]

*Secondo termine*
tensione e corrente sono in quadratura
il termine oscilla tra $\pm |Q|$ 
nei bipoli reattivi (R=0) non c'è dissipazione di energia media!
![[Pasted image 20240108180546.png]]

entrambi i termini oscillano con pulsazione $2\omega$

---
#### Componenti
Chi assorbe la ptoenza reattiva? I componenti reattivi!
Un generico bipolo ha:
![[Pasted image 20240108173352.png]]

*Resistore*: v e i in fase, $\phi=0$ 
Assorbe potenza attiva, non assorbe potenza reattiva
$$Q_{R}=\frac{1}{2}V_{m}I_{m}\sin(0)=0$$
*Induttore*: v è in anticipo su i, $\phi = \frac{\pi}{2}$
Non assorbe potenza attiva ma potenza reattiva
$$Q_{L}=\frac{1}{2}V_{m}I_{m}\sin\left(\frac{\pi}{2}\right)=\frac{1}{2}\omega L\,I_{m}^{2}>0$$
*Condensatore*: i è in anticipo su v, $\phi=-\frac{\pi}{2}$
Non assorbe potenza attiva ma genera potenza reattiva
$$Q_{C}=\frac{1}{2}V_{m}I_{m}\sin\left(-\frac{\pi}{2}\right)=-\frac{1}{2}\omega C\,V_{m}^{2}<0$$
>Non ce le ricorderemo mai queste cose.



## Riassunto
Queste grandezze hanno unità di misura VAR (volt-ampere reattivi)
![[Pasted image 20240108181324.png]]

ed il triangolo è analogo a quello delle impedenze
![[Pasted image 20240108181344.png]]

### Potenza complessa e impedenza
Come si dimostra il legame tra $S$ e $Z$?
per definizione, con rif ass, $V=ZI$ e $S=\frac{1}{2}VI^{*}$ 
$$S= \frac{1}{2}ZI\cdot I^{*}=\frac{1}{2}I_{m}^{2}Z=\frac{1}{2}\left(R+jX\right)I^{2}_{m} $$
- $P=Re(S)= \frac{1}{2}R\,I^{2}_{m}\quad\quad$ 
- $P_{e}=Re(S)=\frac{1}{2}R\,I^{2}_{eff}\quad\quad$ watt 
- $Q=Im(S)=\frac{1}{2}X\,I^{2}_{m}$ 
- $Q_e=Im(S)=\frac{1}{2}X\,I^{2}_{eff}\quad \quad$ volt-ampere reattivi

$\Rightarrow$ così è chiaro che R è responsabile dell'assorbimento di potenza media e Q dell'assorbimento di potenza reattiva

---

![[Pasted image 20240108181501.png]]
bipoli resistivi X=0 -> potenza reattiva Q=0

### Potenza complessa e ammettenza
![[Pasted image 20240108181516.png]]bipoli reattivi R=0 -> potenza attiva P=0