## Concetti 
Usiamo il simplesso per risolvere i problemi di PL, che si basa su concetti geometrici della PL. Li elenchiamo qua.

- Vedi in [[Formulazioni PL]] per sapere come si costruiscono i [[UNIVERSITA/RO/1. PL/definizioni/Modello|modelli]]
- Per questo è utile conoscere la [[Risoluzione Grafica]]
 - Tutta la trattazione dei problemi di PL si basa sul [[TH della PL]]

---

<center>Dal punto di vista algebrico..</center>
**DEF** :
- [[Soluzioni]]
- [[Soluzioni di base]]
- etc etc


<center>Spostandoci ora sul geometrico..</center>

**DEF** :
 L'equazione della *frontiera* si ottiene per un qualunque vincolo sostituendo il predicato con un segno $=$ 
- Queste equazioni rappresentano *iperpiani* nello spazio a $n$ dimensioni. Il predicato $\leq$ o $\geq$ separa i punti che soddisfano il vincolo (iperpiano nella zona ammissibile) rispetto a quelli che non lo soddisfano

- Un qualsiasi punto sulla frontiera della regione ammissibile si trova su uno o più iperpiani definiti dalle corrispondenti equazioni

**DEF** :
 un *vertice ammissibile* è una soluzione ammissibile che non è presente su nessun segmento che congiunge altre altre due soluzioni ammissibili.
 - Una soluzione ammissibile che congiunge altre due soluzioni ammissibili non è un vertice
 - Un vertice è una soluzione di un sistema di due equazioni che definiscono la frontiera.

---

- Dal [[TH di Minkowski-Weyl]] sappiamo che:
1. presi i vertici di un problema, questi sono sufficienti a generare la regione amissibile
2. la base della regione ammissibile vista come politopo è formata dai suoi vertici
>Ogni vertice ammissibile è l'intersezione delle frontiere di n vincoli. 

Che ci porta al  [[TH di equivalenza]].

**QUINDI..**
Un vertice è la soluzione di un sistema di n equazioni che definiscono la frontiera della regione ammissibile.
- Non sempre ogni $n$ equazioni rappresentano un vertice ammissibile. Potrebbe violare uno degli altri $m$ vincoli.
- Non sempre $n$ equazioni hanno soluzione
- A volte un sistema di $n$ equazioni ha più soluzioni, perchè ci sono equazioni ridondanti (vincoli linearmente dipendenti)

Si enuncia il [[TH fondamentale della PL]]
Come conseguenze:
- se c'è almeno un punto interno, c'è almeno un vertice
- se il problema ammette ottimo, questo è una soluzione di base, quindi è un vertice
$\Rightarrow$ <span style="background:#affad1">è sufficiente analizzare solo le soluzioni di base per trovare l'ottimo</span>

---

### Proprietà dei vertici

1. [[TH fondamentale della PL]]


2. Il numero di vertici ammissibili è finito.
	Viene dall'algebra delle matrici: ogni vertice corrisponde ad una soluzione di un sistema.
	Il sistema è rappresentato da $n$ equazioni prese dalle $m+n$ che definiscono la frontiera del poliedro $\Rightarrow$ prese $n$ equazioni posso rappresentare una *base*.
	Con $m+n$ equazioni posso combinarle $n$ e trovare # basi $\equiv$ soluzioni $\equiv$ vertici
	$$\frac{(m+n)!}{m!\,n!}$$
	Che è un numero grande, ma finito. E' l'upper bound del numero di vertici ammissibili.


3. Se un vertice ammissibile non ha vertici adiacienti migliori, allora non ci sono vertici migliori. Enunciato dal [[TH della PL]]


---

## Calcolo soluzioni
Un problema di PL standard può essere scritto in forma standard come $A\overline{x} = \overline{b}$
Posso sfruttare la composizione delle matrici/vettori per riscrivere come:
$$[B|N]\cdot[x_B, x_N] = b$$
Per il calcolo procedo così:
- So che $x_B$ è un vettore a m-n componenti, quindi quelle sufficienti a scrivere una base. 
- So che $x_N$ è il vettore a n componenti superflue che non stanno nella base, quindi li fisso a zero per *"eliminarli dal sistema"*
=> Posso generare con ${n\choose m}$ -> tutte le possibili B matrici di base 

IPOTESI AL SISTEMA LINEARE: deve essere risolubile cioè algebricamente deve valere
$$\large A\vec{x} =\vec{b} \Rightarrow rk(A|\vec{b}) = rk(A) $$ con rango di A=m (numero dei vincoli).

##### Caso n=m
$$ A\vec{x}=\vec{b}\quad\text{tale che }\quad det(A) \ne 0\quad\Rightarrow\quad \vec{x}=A^{-1}\cdot\vec{b}$$
Dunque il vettore x calcolato sarà la soluzione unica esistente.

##### Caso n>m
Osservo di avere $n-m$ gradi di libertà e quindi scelgo queste $n-m$ variabili da fissare e calcolo le soluzioni del problema RELATIVE a questo caso specifico, con queste specifiche variabili a questi specifici valori.

Avendo più variabili di quelle necessarie a formare una base, perchè ricordo $rk(A)=m$ e quindi posso spezzare il vettore $\vec{x}$ così:
$$\large \vec{x} = \begin{bmatrix}\vec{x}_{B}\\\vec{x}_N\end{bmatrix}$$
E di conseguenza i livelli di utilizzo delle risorse - $a_{ij}$ - possono essere aggregati così $A=(B|N)$, matrice tale che $N$ sia relativa alle $n-m$ variabili contenute in $\vec{x}_N$ che è un vettore fissato e posto come nullo.
$$\begin{gather}
\\ \large A\vec{x}=\vec{b} \quad\Rightarrow\quad(B|N)\vec{x}=\vec{b}
\\ \large B\vec{x}_{B}+N\vec{x}_{N}=\vec{b}\quad\Rightarrow\quad \vec{x}_{N=0}\quad\Rightarrow\quad B\vec{x}_{B}=\vec{b} 
\end{gather}$$
