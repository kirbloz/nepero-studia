**DEF** :
 i *sistemi trifase* sono ampiamente utilizzati nei sistemi per la produzione e la distribuzione dell'energia elettrica. Si alimenta il carico mediante 3 o 4 fili.


---
![[Pasted image 20240108211349.png]]
**DEF** :
 si chiama *generatore monofase* un generatore di tensione AC costituito da un rotore che ruota a velocità angolare $\omega$ ed uno statore fisso.
 Il rotore è un magnete permanente o un avvolgimento percorso da corrente DC che genera un campo magnetico $B$ costante
 Lo statore è un cilindro cavo che ospita le spire di un avvolgimento.
 Il flusso magnetico concatenato con l'avvolgimento fisso vale: 
 ![[Pasted image 20240108211343.png]]
---

**DEF** :
 i *generatori trifase* forniscono 3 tensioni sinusoidali uguali in ampiezza ma con $\theta_k$ differenti.
 - In tutto il mondo, hanno una frequenza di circa $50Hz$ 
 >La loro potenza istantanea è costante.
 >E' facile generare il campo magnetico rotante necessario per i motori.
 >Permettono di risparmiare sul cablaggio a parità di potenza trasferita.
 
 Tipica configurazione a stella-induttori con 3 morsetti .
 All'esterno appare come un componente con 3 terminali a 3 tensioni definite rispetto ad un riferimento (interno, centro stella del generatore)
![[Pasted image 20240108211819.png]]

---

Se collego un gen monofase ad un carico trasferisco una $p(t)$ con pulsazione $2\omega$ => forti vibrazioni meccaniche date dalla frequenza di oscillazione
Il gen trifase invece non ha un solo avvolgimento, ma 3 ruotati di $120°$ tra loro e quindi si ottengono 3 flussi sfasati di $120°$
![[Pasted image 20240108211610.png]]

Non solo il flusso, ma anche le 3 tensioni indotte sono sfasate; uguale ampiezza $V_{m}$ e frequenza (da $\omega$) ma con 3 fasi $\theta_k$ diverse.

---
## Fasori generatore trifase

Per ipotesi trascuriamo l'impedenza degli avvolgimenti metallici. Le tensioni sono comunque isofrequenziali, quindi posso passare ai fasori!
![[Pasted image 20240108211921.png]]
A colpo d'occhio si vede:
![[Pasted image 20240108211944.png]]

Osservando graficamente questi tre fasori, si nota che le 3 tensioni costituiscono una *terna equilibrata* (sequenza positiva)[^1]
![[Pasted image 20240108212028.png]]

---

## Circuiti trifase
![[Pasted image 20240108212159.png]]

Lo schema generale prevede un generatore trifase collegato al carico tramite una linea trifase.
- assumo che i conduttori di linea siano equipotenziali

Posso definire le *tensioni di linea* come le tensioni tra i conduttori di linea (equivale a fare le tensioni tra i tre morsetti del generatore)
![[Pasted image 20240108212323.png]]

Esprimiamo graficamente:
![[Pasted image 20240108212459.png]]
![[Pasted image 20240108212447.png]]
![[Pasted image 20240108212509.png]]

---

Concentriamoci ora sul carico
![[Pasted image 20240108212531.png]]
>In italia le tensioni dei generatori hanno ampiezza $230 V$ efficaci, quindi quelle di linea arrivano a $230 \sqrt3 \sim 400\,V$ 

**DEF** :
 Applicando la LKC osservo che $\quad I_{a}+I_{b}+I_{c}=0$
 Un carico trifase si dice *equilibrato*[^1] se le correnti di linea hanno la stessa ampiezza $I_{m}$
 >Si dirà carico equilibrata -> correnti di linea sono terna equilibrata 

### Carichi trifase
![[Pasted image 20240108215115.png]]

**DEF** :
 i *carichi trifase* sono dei carichi che si realizzano come stella (o triangolo) di impedenze.
 - tensioni di fase: quelle ai capi dei bipoli del carico (centro è riferimento)
 - correnti di fase: correnti che scorrono nei bipoli del carico

Analisi di un circuito trifase? 
Dati i generatori e le impedenze di carico, si calcolano le correnti e tensioni *di linea* e *di fase*

---

LASCIO INDIETRO TUTTA LA PARTE SUI CARICHI A TRIANGOLO E A STELLA
SULLA POTENZA ASSORBITA DA UN CARICO EQUILIBRATO ETC