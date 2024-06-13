Una tecnica per generare [[Piano di Taglio|piani di taglio]] durante la ricerca della soluzione ottima per i problemi di PLI. 
Si basea sul generare un taglio o vincolo utilizzando le informazioni associate alla base $B$ della soluzione di base ottima $x^{\ast}$ del rilassamento continuo corrente.

---

Si applica dunque quando $x^*$ soluzione ottima del rilassato (PL associato a PLI) risulta essere frazionaria.

Glossario: 
- [[#Situazione iniziale]]
- [[#Formulare il vincolo]] e la sua [[#Forma standard]]
- [[#Risultato]] e dimostrazione
- [[#Problemi]]

## Situazione iniziale
Ho ottenuto il tableau ottimo associato a $x^*$ (del rilassamento).
Ho almeno una variabile frazionaria $x_{H}$, per cui $\exists$ almeno un $b_{i}$ frazionario. 

- Nella base comparirà $x_H$ con componenti nulle tranne $1$ in corrispondenza di sè stesso (per definizione del tableau)
![[Pasted image 20240204131339.png]]

- Seleziono la riga corrispondente al vincolo di questa $x_H$ tale che:
1. tutte le variabili fuori base moltiplicate per $a_{tj}$ siano intere (e scritti al primo membro)
2. $b_t$ sia frazionario, con $t$ indice della riga alla quale appartiene

Siccome il tableau del simplesso fa riferimento alla forma standard, riscrivendo avrò la *riga generatrice del taglio*:
![[Pasted image 20240204131548.png]]
tale che $x_H$ sia la variabile di base associata alla riga $t$, e $\Phi$ l'insieme delle variabili $x_N$ fuori base.


*Osservazione*: e se ci sono più variabili frazionarie? scelgo quella con la parte frazionaria maggiore, così da "tagliare più in profondità"

## Formulare il vincolo

- Formulo un vincolo:
$$\large(1) \quad \quad x_{H}\,+\, \sum\limits_{j \in \Phi}{\overline a_{tj}\cdot x_{j}} \leq \overline b_t   $$
![[Pasted image 20240204131644.png]]

Ma so che per le proprietà di definizione di $\lfloor \overline a_{tj} \rfloor$ : 
![[Pasted image 20240204131730.png]]
$$\large x_{H}\,+\, \sum\limits_{j \in \Phi}{ \lfloor a_{tj} \rfloor\cdot x_{j}}\,\, \leq \,\, x_{H}\,+\, \sum\limits_{j \in \Phi}{ a_{tj} \cdot x_{j}} \,\, \leq \,\,  b_t $$


- Per cui formulo $(1)$ nella sua versione intera, che per costruzione è violato da $x^\ast$ ma valido $\forall$ altro elemento di $X$.
$$\large (2) \quad \quad x_{H}\,+\, \sum\limits_{j \in \Phi}{ \lfloor \overline a_{tj} \rfloor\cdot x_{j}} \leq \lfloor \overline b_t \rfloor$$
![[Pasted image 20240204131901.png]]
>E' violata da $x^{\ast}$ perchè si ha $j\in \Phi$ $x_{j}^{\ast}=0$ ovvero tutte le variabili fuori base a zero; ma questo implica che $x_{H}^{\ast}$ deve assumere un valore frazionario $b_{t}$ che è maggiore del suo troncamento $\lfloor b_{t}\rfloor$ 
>![[Pasted image 20240204132153.png]]

## Forma standard
Il vincolo così espresso credo lo ritengano brutto quindi ci facciamo le pippe e lo riscriviamo:
Calcolo $(1)-(2)$
![[Pasted image 20240204132327.png]]

Espresso con le "parti frazionarie" delle variabili $A$ e $b$:
![[Pasted image 20240204132454.png]]

- Questa la versione finale
![[Pasted image 20240204132556.png]]
Solo questa version può essere aggiunta al tableau tramite *orlatura* $\Rightarrow$ si va a mantere l'ammissibilità duale richiesta per poter applicare il simplesso duale.
![[Pasted image 20240204133231.png]]
Perchè Gomory implica l'utilizzo del duale?
Perchè devono esistere $a_{tj}$ negativi o nulli


## Risultato
Si può dimostrare che il taglio di Gomory termina per n iterazioni finite e ricade in uno di questi casi:![[Pasted image 20240204132914.png]]

## Problemi
![[Pasted image 20240204154211.png]]

**TRAILING OFF**
![[Pasted image 20240204155509.png]]
Ma quindi cosa è meglio per convergenere nei problemi di PLI? Vedi [[PLI]]















---

>Per costruzione questo vincolo $(2)$ è violato da $x^*$ ma soddisfatto $\forall x \neq x^* \in X$ $\Rightarrow$ poichè se $x^{*}_{j}=0 \quad \forall j \in\Phi$ e se il valore ottimo di una variabile $x^{*}_{H}= b_t$ è frazionario:
$$ x_{H}\,+\, \sum\limits_{j \in \Phi}{\overline \lfloor a_{tj} \rfloor\cdot x_{j}} \,\,\, = \,\,\,x^{*}_{H} :=\, \overline b_{t}\,\,\, > \lfloor \overline b_{t}\rfloor  $$
>se impongo la generica soluzione $\in X$ come $x=x^*$ soluzione ottima da cui ho estratto la riga $t$ generatrice del taglio.

Siccome siamo in PL, posso sempre fare combinazioni lineari di vincoli quindi scrivero $(1)-(2)$:
$$\large \sum\limits_{j \in \Phi}( { \overline a_{tj} -\lfloor\overline a_{tj} \rfloor )\cdot x_{j}}  \geq \overline b_{t}- \lfloor \overline b_{t} \rfloor$$
Ed il vincolo così trasformato con il predicato $\geq$ permette di *tagliare* la soluzione ottima frazionaria ed una "piccola" regione di $P$ senza però intaccare $X \subset P$.

---
devo finire di scrivere la parte con le funzioni + la forma standard