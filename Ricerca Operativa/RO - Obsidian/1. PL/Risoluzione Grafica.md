Metodo risolutivo per [[UNIVERSITA/RO/1. PL/definizioni/Modello|modelli]]. Lo usiamo perchè tanto ci limitiamo a R<sup>2</sup> ed è comodo.

>esempio di mix produttivo ottimale

La funzione obiettivo alla fine è uno scalare, un valore che voglio minimizzare o massimizzare: avrò che f mi identifica un fascio improprio di rette.

**Regione ammissibile**: insieme di tutti i punti che soddisfano tutti i vincoli del problema. Se questi punti sono infiniti la chiamo *poliedro* altrimenti *politopo*.
E' la regione che rimane se al piano cartesiano sottraggo tutte le zone indicate dai vincoli.

**[[Vertici]]**: qualsiasi punto del piano che sia un'intersezione tra [[Vincoli|vincoli]] sturtturali del problema.
>anche gli assi cartesiani sono vincoli! l'origine può essere un vertice

I vertici sono un numero finito perchè al massimo un numero finito di vincoli. In PL ho problemi convessi => insiemi convessi => la soluzione può essere identificata da un semipiano infinito, ma:
==se esiste, l'ottimo di un problema è tra i vertici dello stesso==.

---
Geometria

Unq volta conosciuta la f obiettivo e la regione ammissibile, posso *calcolare la direzione dle gradiente*. Il gradiente di una funzione indica dove questa assume il suo valore massimo:
>se cerco un max, uso il gradiente
>se cerco un min, uso l'anti-gradiente

La funzione obiettivo identifica un fascio di rette improprio, al variare delle variabili decisionali. Il gradiente ==permette di trovare la direzione lungo la quale la funzione obiettivo migliora==, quindi la direzione verso la quale spostarsi (nel fascio di rette trovato)

Quando trovo una retta del fascio che sia tangente alla regione ammissibile sarà SEMPRE in un vertice => così seguendo la direzione del gradiente trovo la soluzione ottima.
Se è tangente in almeno due punti => corrisponde ad un vincolo => il problema ha [[Soluzioni multiple]], che sono gli infiniti punti della regione ammissibile giacienti sulla porzione di retta intersecata.

---