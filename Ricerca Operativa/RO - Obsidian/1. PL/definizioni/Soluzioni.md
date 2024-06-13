In generale in un problema PL in forma standard possiamo trovare delle **soluzioni**, dei punti che risolvono le equazioni del sistema preso in causa.

Comunque per avere queste mezze definizioni applicate, vai a leggerti la pagina sul simplesso.
# Soluzioni ammissibili
**DEF** :
 Le **soluzioni ammissibili** sono tutte le soluzioni che oltre a soddisfare i vincoli, rispettano anche i criteri di positività delle variabili considerati. Sono tutti i punti che rientrano nella regione ammissibile.

# Soluzioni di base

**DEF** :
 Se oltre ad essere ammissibil, le soluzioni risolvono un sistema ad $n$ equazioni preso dalle $n+m$ del problema in forma standard - allora si chiamano anche *soluzioni ammissibili di base*.
- la matrice $B$ è invertibile e dunque posso calcolare il valore delle varibili di base $\Rightarrow$ la soluzione è anche un vertice $\Rightarrow$ si chiamano *soluzioni ammissibili di base*
> Vedi legame vertici-soluzioni in [[TH di equivalenza]]; si possono usare soluzione e vertice intercambiabilmente

Si possono suddividere le soluzioni di base in 
- degeneri
- non degeneri

## Soluzioni Degeneri
 **DEF** :
 
 >Caso in cui due o più variabili possono essere scelte come variabili uscenti dalla base, ovvero se trovo due o più variabili fuori base con CCR negativo e minimo.
 > Ricordo cosa succede quando porto una variabile in base:
 > - se $x_{i}\in \overline x_B$ significa che il vertice considerato è l'intersezione tra diversi iperpiani. Per stare su un iperpiano, bisogna azzerare la su [[Variabili di Slack|variabile di slack]].
 > - tutte le variabili di base che possono essere scelte raggiungono il valore zero simultaneamente al crescere del valore della variabile entrante 
 > - le variabili non scelte assumono valore nullo comunque!
 > - se una di queste vaiabili di base degeneri mantene il suo valore zero finchè viene scelta per uscire, allora anche quella entrante dovrà mantenere valore zero => FO non cambia => soluzioni ciclanti
  
 ---
 POV ALGEBRICO
 Il calcolo delle soluzioni mi porta a trovare una variabile associata al vettore $\vec{x}_{B}\geq0$  significa che oltre alle n variabili di $\vec{x}_N$ trovo almeno una variabile nulla in più. Come faccio a decidere quale tra queste va presa nella base o meno? 
 
 Le soluzioni degeneri sono sempre problematiche perchè i vertici degeneri sono caratterizzati dal fatto che sono individuati da più vincoli di quelli necessari => quando ho un sovrannumenro di vincoli si dice che ho [[Vincoli ridondanti]].
 
 >Un vertice degenere è associato a più basi. Ho tanti modi per settare le variabili fuori base (dal sovrannumero) e quindi o tante basi per ogni veritce.

Entra nel file per vedere altro.
#### Vertici degeneri in Rn
In R<sup>2</sup> se ho un *vertice degenere* ho di sicuro almeno un vincolo ridondante.
Posso anzi DEVO eliminare quel o quei vincoli, per semplificare il problema.

In R<sup>n</sup> invece questo non vale. In generale i vincoli ridondanti sono sintomo di vertici degeneri che dunque esistono associati a più basi, ma sono essenziali per individuare la regione ammissibile perchè altrimenti crolla la struttura del problema.

>Esempio: una piramide a base quadrata ha il vertice in alto che è intersezione tra 4 rette, quindi le 3 essenziali + 1 extra. Se però togliessi una sola a caso tra queste, non avrei più una piramide!
 
## Soluzioni di base non degeneri
 Il calcolo delle soluzioni trova solo $\vec{x}_B$ strettamente positive, arrivo ad avere un vettore $\vec{x}=(\vec{x}_B,\vec{x}_N)$ con $\vec{x}_{b}>0$ e $\vec{x}_{N}=0$ imposto per fissare i gradi di libertà dati da $n-m$.

## Soluzione illimitata
Se durante una generica iterazione non si trova nessuna variabile idonea a essere portata fuori base significa che almeno una variabile già in base può essere incrementata all'infinito senza che comporti valori negativi per nessuna delle variabili in base correnti.

## Ottimo multiplo

**DEF** :
 un problema di PL con più soluzioni ottime e regione ammissibile limitata, possiede almeno due vertici. 
 Inoltre ogni combinazione convessa di due vertici/soluzioni trova un altra soluzione ammissibile, ma se i due vertici presi sono ottimi, allora ogni loro combinazione convessa sarà ancora una *soluzione ottima*, detta *multipla*.
 >multipla perchè sono tanti (infiniti) punti diversi; per essere ottimi assumono TUTTI lo stesso (ottimo) valore della FO