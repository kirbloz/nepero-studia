Rimando lo schemino in [[appunti per esercizi#Simplesso duale]]

---

**DEF**
 chiamo *algoritmo duale* un qualsiasi algoritmo iterativo che parta da una soluzione ammissibile per il Duale puntando a ottenere la condizione di ammissibilità del Primale ( $\equiv$ che è l'ottimalità del Duale)

*QUANDO SI USA?*
 Ho già risolto un problema primale P, ho determinato $x^{\ast}$ e ci vengono imposti dei NUOVI VINCOLI $$\alpha ^{\intercal}x \leq \alpha_{0}$$
## Procedimento
Prima di tutto quando in un problema di PL già risolto si aggiungono dei vincoli, si porta questi ultimi in forma standard $$\alpha ^{\intercal}x + x_{n+1}= \alpha_{0}$$
*DUE SCENARI POSSIBILI*

<center>1. x * RIMANE AMMISSIBILE</center>
 allora $x^{\ast}$ rimane anche ottimo perchè soddisfa già tutti i vincoli precedenti ottimalmente.
 >Potrebbe portare ad una soluzione ottima multipla, me ne accorgo se $x_{n+1}=0$

<center>1. x * DIVENTA NON AMMISSIBILE</center>
significa che la nuova variabile $x_{n+1}<0$, essendo tutti gli altri ammissibili da prima questa è l'unica che può crear problemi.

La soluzione precedente viola il nuovo vincolo e quindi bisogna ri-opttimizzare.
Secondo la teoria della dualità il vertice corrispettivo di $x^{\ast}$ nel Duale sarà ammissibile e quindi posso passare ad iterare il simplesso da lì, senza dover riscrivere P da capo.



---

![[Pasted image 20240204134937.png]]
![[Pasted image 20240204134945.png]]Tutto ok.

![[Pasted image 20240204135003.png]]
![[Pasted image 20240204135013.png]]


SIMPLESSO DUALE:
![[Pasted image 20240204135201.png]]


