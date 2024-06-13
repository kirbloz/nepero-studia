**DEF** :
 Data una formulazione matematica si definisce *preprocessing* l’insieme di tutte le operazioni che possono essere compiute al fine di migliorare la formulazione:
 - [[#Bound stringenti]]
 - [[#Fixing variabili]] per eliminarle
 - [[#Disuguaglianze logiche]]

---

## Bound stringenti
Si applica nei problemi PLI laddove appare un vincolo di tipo $x_{i}\leq My_i$. Questo perchè se fisso $M$ in modo intelligente posso convergere all'ottimo più velocemente!
>con questa tecnica si spera di stringere sulle coordinate il più possibile (cerco il convex hull). si evita l'instabilità numerica.
- se le variabili decisionali hanno un <span style="background:#ff4d4f">UPPER BOUND comune</span>, allora $M=UB$


![[Pasted image 20240203213917.png]]

## Fixing variabili
Sfrutta tecniche di probing per <span style="background:#ff4d4f">stabilire a priori il valore ottimo di alcune variabili</span>.
Siano:
- $z_{PL}$ il valore ottimo del rilassamento continuo (P)
- $z_H$ il valore di una soluzione ammissibile qualsiasi intera (X)
- $GAP = z_{PL}-z_H$     (UB-LB)
- $x^{PL}_{j}=0$ variabile $x_{j}$ che nella soluzione ottima del rilassamento è nulla e $c_{j}$ il suo CCR

CONDIZIONE:
	se $c_{j}> GAP\quad \Rightarrow \quad x_{j}^{\ast}=0$ 
	se portando la variabile $x_{j}$ in base (=diventa pos) allora la funzione obiettivo peggiora tanto da diventare $z'_{PL} \geq z_H$ significa che mi sto allontanando dall'ottimo
	$\Rightarrow$ posso tenerla fissa a 0 

![[Pasted image 20240203215023.png]]

## Disuguaglianze logiche
Si basa sul semplificare insiemi di vincoli osservando il comportamento del problema. L'idea è trovare una riformulazione che renda almeno un vincolo ridondante.

esempio:
 ![[Pasted image 20240203220320.png]]