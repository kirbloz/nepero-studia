Glossario:
- [[#Costruzione del ragionamento]]
- [[#Unimodularità]] e [[#Totale Unimodularità]]
- [[#Come si dimostra che A è TUM?]]

## Costruzione del ragionamento
Si consideri:
![[Pasted image 20240203221015.png]]
A e b interi.

*Domanda del secolo*
Sotto quali condizioni una generica soluzione di base ammissibile $x^{\ast}$ ha componenti frazionarie?


Sia $B$ la base associata alla soluzione generica ammissibile $x^\ast$. Allora $x^{\ast}$ ha componenti frazionare $\Leftrightarrow$ $B^{-1}b$ non è intero.

*Com'è fatta $B^{-1}$?*
![[Pasted image 20240203221237.png]]
$B$ è intera $\Rightarrow\,\,a_{ij} \, \forall i,j$ interi $\Rightarrow$ $B^{-1}$ intera se il suo determinante è $\pm1$


---

# Unimodularità

**DEF** :
 Una matrice intera $A$ di dimensione $m \times n$ con $m \leq n$ si dice *unimodulare* se per ogni sua sottomatrice quadrata $B$ di ordine $m$ vale 
 $$\det(B) \in \{-1,0,+1\}$$

![[Pasted image 20240204122832.png]]

---
## TEOREMA 1
Sia $A$ unimodulare e $b$ intero.
Allora il poliedro continuo $P=\{  x \geq 0 \,:\, A x =  b\}$ ha solo vertici interi.

> Teorema importante si ok però la definizione di quel poliedro è vincolante, mi limita nella casistica a cui applicare il teorema. Devo trovare un ragionamento simile anche per i problemi con variabili di slack.

*Dimostrazione*
 ![[Pasted image 20240203222131.png]]
 ![[Pasted image 20240203222140.png]]

---

**DEF** :
 Una matrice intera $A$ di dimensione $m \times n$ si dice **totalmente unimodulare** se 
 $\det(Q) \in \{-1,0,+1 \}$ vale per ogni singola sottomatrice quadrata $Q$ di ordine qualunque.
 
>ordine che va da 0 ad m. quindi anche i singoli elementi sono uno di quei tre valori

# Totale Unimodularità
**DEF** :
 Una matrice intera $A$ di dimensione $m \times n$ si dice *totalmente unimodulare* o TUM, se vale  $\det(Q) \in \{-1,0,+1\}$ per ogni sua sottomatrice quadrata $Q$ di qualunque ordine.

---

## TEOREMA 2
Sia $A$ TUM e $b$ intero.
Allora il poliedro  $P=\{ \underline x \geq 0 \,:\, A\underline x = \underline b\}$ ha solo vertici interi.

*Dimostrazione*
 ![[Pasted image 20240203224719.png]]
 ![[Pasted image 20240203224729.png]]




## Come si dimostra che A è TUM?

Potrei enumerare tutte le sottomatrici, oppure 
sfruttare queste condizioni semplici:

![[Pasted image 20240204122917.png]]
![[Pasted image 20240204123023.png]]


*Condizione necessaria non sufficiente*
![[Pasted image 20240203225657.png]]

*Condizione sufficiente non necessaria*
![[Pasted image 20240203225713.png]]

![[Pasted image 20240203225723.png]]
![[Pasted image 20240203225733.png]]