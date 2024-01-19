Componenti dinamici inseriti dal progettista, oppure presenti (anche in circuiti che si vorrebbero resistivi) come elementi parassiti. *Sono descritti da un’equazione differenziale del primo ordine.*
- Risoluzione semplice, modello irrealistico, ma le proprietà generali si estendono facilmente ai sistemi di ordine superiore.
	Circuiti RC e RL: sono perfettamente duali!


## Senza interruttori
### Risposta libera
$$\begin{array} \large \frac{dx(t)}{dt}+\frac{1}{\tau}x(t)= 0\\ x(t)= x(0) \,\,e^{-t/\tau}\end{array}$$
Interpretazione fisica: scarica del condensatore/induttore.
Ha una durata di circa $4-5\tau$ e poi diventa trascurabile.

### Risposta libera e forzata
$$\large\begin{array} \large \frac{dx(t)}{dt}+\frac{1}{\tau}x(t)= \frac{x_p}{\tau}\\ x(t)= [x(0)-x(\infty)] \,\,e^{-t/\tau} + x(\infty)\end{array}$$
Se il circuito è stabile allora $x(t)$ tende a $x_p$ all'infinito

*Caso generale RC*
Si considerano circuiti contenenti un solo condensatore, un numero arbitrario di elementi resistivi e sorgenti ideali costanti.
Si calcola l'equivalente Thevenin della parte resistiva e poi si applica la formula.

*Caso generale RL*
Si considerano circuiti contenenti un solo induttore, un numero arbitrario di elementi resistivi e sorgenti ideali costanti.
Si calcola l'equivalente Norton della parte resistiva e poi si applica la formula.

### Costante di tempo
Ci aiuta a interpretare come evolve la risposta. 
Possiamo vederlo in termini di "riduzione della distanza" tra $x(0)$ e $x(\infty)$

CARICA: $x(\infty) > x(0)$
SCARICA: $x(\infty) < x(0)$ 


## Con interruttori
Non posso usare TH/NO perchè il circuito diventa tempo variante.
Sfrutterò il fatto che $v_c$ ed $i_L$ sono grandezze continue nel tempo e dunque posso calcolare il valore iniziale (immaginando che l'interruttore commuti dopo essere rimasto fermo per molto tempo):
- Si calcola $v_C(0^-)$ o $i_L(0^-)$ a regime.

La commutazione in $t=0$ non influenza le grandezze citate.

Immagino che l'interruttore rimanga fermo all'infinito, e quindi il circuito sia *a regime*. Procedo come per il valore iniziale: 
- Si calcola $v_C(\infty)$ o $i_L(\infty)$ a regime.
Con un solo accorgimento però! La tensione sul condensatore sarà costante, si comporta come un CA. La corrente sull'induttore sarà costante, si comporta come un CC. 
Il valore finale si calcola *risolvendo un circuito resistivo equivalente*.

![[Pasted image 20240105191040.png]]
![[Pasted image 20240105191050.png]]
# Algoritmo generale
Se vogliamo calcolare delle variabili circuitali che non siano $v_C$ o $i_L$, TH/NO non ci aiuta nemmeno se non ci sono interruttori. 
Le altre variabili potrebbero anche essere discontinue!

Si dimostra che con eccitazione costante e $R_{eq} > 0$, qualunque tensione o corrente $x(t)$ evolve in modo esponenziale con un $\tau$ fissato dal circuito.
Si sfrutterà il principio di sostituzione.

**PER CONDENSATORI**
![[Pasted image 20240105191424.png]]

**PER INDUTTORI**
![[Pasted image 20240105191432.png]]
