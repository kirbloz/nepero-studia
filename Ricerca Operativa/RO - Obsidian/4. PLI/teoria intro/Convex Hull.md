>Se si elimina il vincolo di interezza sulle variabili del modello si ottiene il corrispondente rilassamento continuo.

La <span style="background:#fff88f">regione ammissibile di un problema di PLI </span>si descrive come$$ X = P \cap Z^{n} $$
dove $P=\{x \geq0 : Ax \geq b\}$ è la <span style="background:#affad1">regione ammissibile del rilassato</span> $\Rightarrow$ $X$ risulta essere un reticolo di punti, quindi non convesso.

---

**DEF** :
 Sia $X=\{x^{1}, x^{2}, \dots x^k\}$ l'insieme di soluzioni intere ammissibili di un problema di PLI limitato e finito. 
 Definisco *convex hull* di $X$ oppure *CH($X$)* l'insieme finito di punto così scritto
![[Pasted image 20240203192252.png]]

>E' un poliedro convesso rappresentante la formulazione ideale del problema di PLI tale che $CH(X) \subset P$ dove $P$ è la regione ammissibile di un qualsiasi rilassamento continuo. Cioè CH(X) è contenuto da qualsiasi altro rilassamento continuo $\Rightarrow  CH(X)$ è il rilassamento continuo ottimale! 


Geometricamente:
![[Pasted image 20240203190723.png]]