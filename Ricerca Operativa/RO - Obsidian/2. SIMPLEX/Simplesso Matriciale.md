# Idea
L'approccio generale del simplesso è quello di ottenere una sequenza di SAB sempre migliori fino a quando non si raggiunge una soluzione ottima.

1. Il simplesso parte da una situazione con:
- SAB iniziale nota $\Rightarrow$ variabili dentro e fuori base note
	Date queste variabili $x = [ x_B\,; \,\,\underline 0\,\,]$, allora si calcola la prossima SAB, migliore di questa.

2. La *soluzione di base* risultante è la soluzione di un sistema di $m$ equazioni $[A\,,\, I] [x] = b$ in cui LE $n$ variabili NON di base tra le $(n+m)$ del vettore $x$ sono fissate a zero.

3. Rimane solo quindi $B\,x_B=b$ 
   La i valori della soluzione sono i valori delle variabili $x_{B}= B^{-1}b$ 
   Il valore ottimo della FO varrà $z*= c_{B}x_{B}= c_{B}B^{-1}b$

# Svolgimento

Prima si porta il problema in [[Forma Standard]].
- Se non si ha una soluzione iniziale nota.. [[Due Fasi]]

Poi si..
## Costruzione tableau

si

## Scelta del pivot
>problema di min

Quale colonna j con CCR positivo faccio entrare in base?
Come risolvo i casi di parità delle righe?
**Obiettivo**: avvicinarsi all'ottimalità ed evitare la [[degenerazione ciclante]].

*Criteri possibili*:
1. colonna $j$ con CCR più negativo
2. colonna $j$ che produce il massimo decremento di $z$
3. metodo di Bland

*Nota Bene*
In generale il <span style="background:#affad1">pivoting non conserva l'ammissibilità</span>. Scegliendo le variabili IN e OUT dalla base, il pivot potrebbe portarmi ad una soluzione non ammissibile.
Il pivoting punta solo a migliorare il risultato.
<span style="background:#b1ffff">E' la regola per la determinazione della variabile che esce a garantire l'ammissibilità della nuova soluzione di base</span>

### Metodo di Bland 
1. si sceglie la colonna con coefficiente minore (variabile entrante)
2. si sceglie la riga (variabile uscente) con pivot positivo e rapporto tra termine noto e coefficiente minore
![[Pasted image 20230429211140.png]]


## Pivoting
Cerco man mano le SAB..
Vedi come [[Simplesso Matriciale#Scelta del pivot (prob di min)|scegliere l'elemento pivot]].
Poi si trasforma la tabella per mantenere la forma canonica della matrice.

---

![[Pasted image 20230429205152.png]]
Supongo di far entrare $x_q$ con $m<q\leq n$ e uscire $x_p$ con $l\leq p\leq m$ (lo scambio è possibile solo se il coeff $a_{pq} \ne 0$)

1. Divido la *p-ma* riga per $a_{pq}$        (riga pivot) / (elemento pivot)
2. Per ogni $i= 1 \dots m$ tale che $i \ne p$ si sottrae alla *i-ma* riga la *p-ma* moltiplicata per $a_{iq}$ il coeff dell'elementino che incrocia riga e colonna. La *q-ma* colonna diventa un vettore della base canonica 
$$ \begin{matrix}\begin{align*} 0 \\ \dots \\ 0 \\  \text{elemento di posto (p,q)} \rightarrow 1 \ \\ \dots \\ 0 \\ \end{align*} \end{matrix}$$


![[Pasted image 20230429210010.png]]

## Test di ottimalità
> problema di minimo

Per sapere se la soluzione trovata è ottima basta guardare l'ultima riga:
se esiste anche solo un elemento $x_j$ che sia vantaggioso portare in base, allora non è l'ottimo.
Se invece tutti i CCR sono non negativi ($CCR \geq 0$) allora modificare la base troverebbe una soluzione che non può che altro AUMENTARE il valore di FO => ottimo!

---

# Analisi tableau
![[Pasted image 20240125191007.png]]![[Pasted image 20240125191018.png]]
![[Pasted image 20240125191025.png]]

e tutto torna! 
Lo stesso risultato si raggiunge se faccio i passaggi algebrici sul modello del problema.