# POV algebrico
La funzione obiettivo ed i vincoli sono funzioni lineari nelle incognite (non appaiono prodotti di incognite)
![[Pasted image 20230227191842.png]]

**DEF** :
 La *funzione obiettivo* è un valore scalare definito dal prodotto interno (scalare) tra la trasposta del vettore delle costanti C ed il vettore delle variabili X. Detta anche funzione $Z$
>dimensioni: (1xn)(nx1) = 1, il prodotto commuta

**DEF** :
 I *vincoli*  $\sum\limits_{i} a_{ij}x_{j} = b_{i}$   sono $m$ e le *variabili decisionali* $x_{j}$ sono $n$.
 La matrice descrittiva A è (mxn). Il vettore b sono i termini noti (mx1)
- Le variabili $x_{j}$ sono le incognite e si dicono anche livelli di attività

**DEF** :
 i coefficienti $c_j$ sono detti *coeff di costo ridotto* e moltiplicati a $[ \overline x ]$ danno la FO. 
 Indicano la variazione del valore di $Z$ per ogni incremento unitario dalla corrispettiva variabile $x_{j}$

**DEF** :
 i termini noti $b_{i}$ sono le quantità di risorsa $i$ disponibile per l'allocazione alle varie attività $j$.

**DEF** :
 i coefficienti $a_{ij}$ della matrice dei vincoli rappresentano òla quantità di risorsa $i$ cosumata da una unità di attività $j$.



---
*Forma canonica*
 ![[Pasted image 20230228115701.png]]
Dalla forma canonica è opportuno passare alla standard tramite la standardizzazione.

*Forma standard*
 ![[Pasted image 20230228115716.png]]
La risoluzione si svolge sempre usando la forma standard.
Dall'algebra abbiamo le regole per sapere se ha soluzioni e quante.

>Supporremo che la forma standard con $m < n$ implica avere una forma matriciale del sistema lineare ove A (mxn), x (nx1) e b un vettore colonna (mx1) che contiene vincoli LI.

**NUMERO SOLUZIONI**
Diremo che il *rango* della matrice A sia $m$ e quindi
- se $m = n$ esiste una sola soluzione, $x = A^{-1} \cdot b$
- se $m < n$ esistono infinite soluzioni, con $(n-m)$ gradi di libertà.

Si può fissare $n-m$ variabili arbitrariamente per calcolare/ricavare dal sistema le restanti $m$ variabili come fosse un problema standard con rango $m$.

---