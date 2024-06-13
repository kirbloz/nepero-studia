Glossario:
- [[#Definizione]]
- [[#Classificazione]]
- rimando a [[Zero Half Cuts]] e [[Taglio di Gomory]]

---

>IPOTESI: Sono sempre nell'ambito della PLI, quindi $X=P \cap Z^n$ ove $P$ è il poliedro del rilassamento continuo (PL) e $X$ il reticolo di punti ammissibili (PLI).

## Definizione

**DEF** :
 Dato $x^{*}\in P$ si dice *piano di taglio* una disuguaglianza $\alpha^{t}\underline x \leq \alpha_0$ tale che valgano:
 1. $\alpha^{t}\underline x \leq \alpha_0$ soddisfatto $\forall \underline x \in X:= P \cap Z^n$ 
 2. $\alpha^{t}x^{*}>\alpha_0$ 
- Il piano di taglio è un vincolo frutto di un problema di *separazione di una soluzione ottima $x^*$ da un insieme discreto* $X$ 

>E' fondamentale che il piano elimini la soluzione selezionata ed un'area di SOLI punti frazionari, senza ridurre le possibili soluzioni intere (non deve ridurre i punti di $X$ che stanno in $P'$ )
>Questi tagli non ci avvicinano a CH(X) globalmente, solo "localmente" attorno alla soluzione ottima del rilassato, finchè si ottiene un $x^{\ast}_{PL}$ intero

---

## Classificazione
E' ruolo dell'esperto e modellizzatore saper introdurre tagli efficienti. Gurobi/PC/algoritmi non conoscono il significato semantico dei modelli o delle loro parti.
Noi studiamo i general purpose che siano [[Zero Half Cuts]] e [[Taglio di Gomory]]

![[Pasted image 20240204130553.png]]