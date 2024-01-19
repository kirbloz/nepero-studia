Per un'introduzione vedi [[Risposta e Regime]].

Immagino dei circuiti dinamici lineari a cui impongo una forzante sinusoidale.
**DEF** :
 Quando la risposta transitoria si esaurisce e tutte le variabili diventano sinusoidali con la medesima frequenza, diremo allora che il circuito è in *regime sinusoidale*.

### RC
![[Pasted image 20240106183055.png]]
Ingresso sinusoidale a pulsazione omega ![[Pasted image 20240106183109.png]]
Trovo la solita equazione delle tensioni:
![[Pasted image 20240106183206.png]]

La soluzione continua ad avere la forma simile al caso di forzante costante:
![[Pasted image 20240106183241.png]]
Esaurito il transitorio (blu) rimane e si parla solo di *regime sinusoidale* alla pulsazione $\omega$.

## Calcolo risposta permanente
L'equazione nel dominio del tempo che descrive il comportamento del circuito:
![[Pasted image 20240106183351.png]]

So che la risposta permanente è quella nella forma in rosso, dunque è la soluzione particolare dell'equazione differenziale. 
So anche che per stabilirla senza ambiguità devo scoprire i valori di $A$ e $\theta$ dunque la sostituisco così com'è nell'equazione.
>Inserisco la soluzione particolare nell'equazione.

ATTENZIONE! Qui posso evitarmi la pena di inserire varibili, fare integrali e derivate e cicì e cicià se passo al dominio dei fasori.
![[Pasted image 20240106183610.png]]![[Pasted image 20240106183621.png]]

Una volta risolta l'equazione per il fasore, ottengo un oggetto tipo così:
![[Pasted image 20240106183715.png]]
Che posso esprimere con chiarezza se calcolo il modulo $\vert V_C \vert$ e la fase $\angle V_C$  

## Proprietà
In ogni circuito lineare e stabile con generatori indipendenti sinusoidali a pulsazione $\omega$ si raggiunge un regime sinusoidale a $\omega$.
Tutte le variabili circuitali hanno comportamento sinusoidale con la stessa pulsazione.
Il regime non dipende dalle condizioni iniziali, infatti quelle influenzano solo il regime transitorio.

La *risposta a regime* si ottiene con il metodo dei fasori risolvendo circuiti resistivi fittizi.

## Potenza
Vedi [[Potenza in regime sinusoidale]]