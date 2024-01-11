IMPEDENZA:
La caratteristica è:
$$ \large v = \frac {I}{jwc}$$
E' un'impedenza reattiva pura. 
In DC $\omega=0$ è un circuito aperto (impedenza infinita)
In AC $\omega \rightarrow \infty$ è un corto circuito (impedenza nulla)
In parallelo si sommano.

---

Bipolo non lineare descritto da una caratteristica differenziale.
Si oppone alle variazioni di tensione.
$$i_{C}(t)=C \cdot \frac{dV}{dt} \quad \quad \quad v_c = \frac{1}{C} \int I\,dt=QC$$

##### POV FISICO - GENERALE
 Se si applica tensione ai suoi capi, il *C* assorbe o generea una corrente che provoca uno spostamento di cariche (l'integrale della formula) che si <span style="background:#d3f8b6">oppone</span> alla tensione applicata.
 Per questo si dice che *il condensatore si oppone alle variazioni di tensione memorizzando uno stato di carica*.

 > In DC dopo t sufficiente la tensione ai suoi capi è nulla.


### COLLEGAMENTI TRA CONDENSATORI

Se sono [[Condensatori in parallelo |in parallelo]] dalla LKC si ha:
$$ i(t) = \sum\limits C_i\frac{dv}{dt} \quad \quad \quad C = C_{1}+ ... +C_n$$
La capacità totale è la somma di tutte le singole e la tensione che cade ai loro capi è la medesima.
Scorrono correnti diverse con stessa tensione.


Se sono [[Condensatori in serie|in serie]] dalla LKT si ha:
$$ v(t) = \sum\limits \,\,\left[\,\,\,v_{i}\left(t_{0}\right)+\frac{1}{C_{i}}\int_{t_{0}}^{t}i(x)dx\,\,\,\right]\quad \quad \quad C=\frac{1}{C_{1}}+...+\frac{1}{C_{n}}$$
La capacità totale è la somma dei reciproci delle singole e tensione pari alla somma delle tensioni ai capi di ciascuna.
Scorrono correnti uguali con diverse tensioni.