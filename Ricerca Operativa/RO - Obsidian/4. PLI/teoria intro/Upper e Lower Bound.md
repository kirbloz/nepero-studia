>Caso problema di minimo

**DEF** :
 In ogni problema di PLI è verificato che $X\subset P$ dunque posso dire che$$z_{PL} = min \{ c^{t}  x:  x \in P \} \quad \leq \quad min \{ c^{t}  x:  x \in X \} = z_{PLI} $$
 Quindi $z_{PL}$ - l'ottimo del rilassato - sarà sempre un limite inferiore o *LOWER BOUND* per il valore $z_{PLI}$ 


**DEF** :
 Invece il valore di <span style="background:#b1ffff">una qualsiasi soluzione ammissibile</span> (di solito iniziale) per il problema intero $\hat x \in X$ fornisce un limite superiore o *upper bound* per il valore $z_{PLI}$ 
 $$ min \{  c^{t} x :  x \in X\} = z_{PLI} \leq  c^{t}\hat x$$
>non ha senso studiare un rilassato che peggiora i risultati già trovati in modo euristico o automatico sul PLI

---

copilot:
Il rilassamento continuo di un problema PLI si ottiene rimuovendo la restrizione di interezza sulle variabili. Questo rilassamento fornisce un lower bound per il valore ottimo del problema PLI originale nel caso di minimizzazione, o un upper bound nel caso di massimizzazione.

Ecco perché: se permettiamo alle variabili di assumere valori reali anziché interi, stiamo espandendo lo spazio delle soluzioni possibili. Di conseguenza, la soluzione ottima del problema rilassato è almeno buona quanto la soluzione ottima del problema originale (nel caso di minimizzazione, è minore o uguale; nel caso di massimizzazione, è maggiore o uguale). Quindi, il valore ottimo del problema rilassato fornisce un bound per il valore ottimo del problema PLI originale.

Tuttavia, è importante notare che mentre il problema rilassato può essere risolto in modo efficiente utilizzando metodi di programmazione lineare, la soluzione ottenuta potrebbe non essere intera, e quindi potrebbe non essere fattibile per il problema PLI originale. In tali casi, sono necessarie ulteriori tecniche, come il metodo del branch and bound, per trovare la soluzione ottima intera.