![[Pasted image 20231205182930.png]]

Tipo di memoria volatile che dipende esiste quando c'è alimentazione - se la si toglie, i dati van perduti.

- E' una memoria statica basata sull'implementazione di FF
- Da $M$ linee di indirizzo (ADDR) si generano $2^M$ linee di selezione BSi
- Il bus-dati riceve molte linee; ci sono problemi di fan-out (statico e dinamico)

Questo circuito campiona il dato sulla linea READ, basandosi su di un segnale che quando è attivo, impone la lettura del dato.
>Sengale BS dice al tristate "leggi bambo!"

