Glossario:
- [[#Interpretazione Economica]]
- [[#Interpretazione Algebrica]]
- Vedi [[Analisi di Sensitività]] per continuare
## Interpretazione Economica

**DEF**:
 La soluzione ottima del duale $\lambda^\ast$ prende il nome di vettore dei *prezzi ombra*.
 " Ogni sua componente mi dice quanto sono disposto a pagare per avere una unità in più della corrispondente risorsa del primale. "
>Altra interpretazione: " le $\lambda ^ {\ast}_{i}$ rappresentano il profitto addizionale che si ottiene quando la risorsa $i$-esima aumenta di un'unità nell'ipotesi che i vincoli saturi (attivi, variabili fuori base), rimangano gli stessi"

Interpretazione economica
![[Pasted image 20240202131956.png]]


## Interpretazione Algebrica

I *CCR del duale* ($b$), ed indicano il contributo in termini di funzione obiettivo per ogni unità di cui venga aumentata la disonibilità della risorsa vincolata dalla relativa variabile di slack (P).
Le componenti della soluzione del duale - $\lambda_i$ - sono gli *shadow prices*, perchè per ogni variazione di risorse vincolate, dobbiamo "pagare" un quantitativo che si rispecchia nella funzione obiettivo.. vedi sotto la derivata.

DERIVATA $z$ RISPETTO AI $b_i$
![[Pasted image 20240202132642.png]]
dim:
 ![[Pasted image 20240202133107.png]]

---

<center>IN SINTESI</center>
A fronte di un $\Delta b$ del problema primale P:
$$\begin{array}
\\ z+\Delta z= c^{\intercal}_{B}B^{-1}b+c^{\intercal}_{B}B^{-1}\Delta b
\\ =c^{\intercal}_{B}B^{-1}b+ \lambda^{\intercal \,\ast}\Delta b
\end{array}$$
![[Pasted image 20240202140230.png]]
>- Ricordo che $\lambda^{\intercal\,\ast}=c^{\intercal}_{B}B^{-1}$ è la soluzione ottima del Duale - con $B$ base ottima del primale.
>- Considereremo sempre $\Delta b = [0;b_i;0]$ ovvero variazioni su UN SOLO termine noto alla volta. Se ce ne fossero di più, allora si considerano tanti casi per ogni valore alla volta.

**Nota**
<span style="background:#fff88f">I valori dei prezzi ombra rimangono tali fintanto che la soluzione ottima non varia.</span>
Esiste uns "soglia" alla variazione di $b_i$ possibile ![[Pasted image 20240202140504.png]]

Dal POV geometrico si capisce bene..
modificare il termine noto di un vincolo significa traslarlo (in gradiente o antigradiente), ma la funzione obiettivo rimane FERMA!
Ci sarà inevitabilmente un momento in cui la traslazione provoca un cambiamento del vertice ottimo

---




