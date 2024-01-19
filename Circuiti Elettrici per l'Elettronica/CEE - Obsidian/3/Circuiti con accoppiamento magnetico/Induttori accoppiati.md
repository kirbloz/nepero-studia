Rendiamo il modello di trasformatore ideale un po' più realistico.
Consideriamo due bobine vicine, accoppiate magneticamente.
E' un bipolo dinamico, lineare, resistivo.
Se $M=0$ allora si ottengono degli induttori classici, che non si influenzano.

Accendiamo una alla volta le due porte, facendo prima scorrere una corrente in una bobina e poi nell'altra.

![[Pasted image 20240111092251.png]]

1. Nella prima scorre una corrente $i_1(t)$ mentre $i_2=0$
- il flusso magnetico nella bobina 1 è $\phi_{11}=L_1i_1$
- il flusso magnetico nella 2 è $\phi_{21}=M_{21}i_{1}$

2. Se accendiamo solo la corrente $i_2(t)$ invece si ha l'opposto
- $\phi_{22}=L_{2}i_{2}$
- $\phi_{12}=M_{12}i_{2}$

Si chiama $L_{i}$ la *auto-induttanza* della bobina $i$
SI chiama $M=M_{12}=M_{21}$ la *mutua induttanza*

I flussi complessivi sono 
$$\phi_{1}=\phi_{11}+\phi_{21}=L_1i_1+Mi_2\quad\quad\phi_{2}=\phi_{22}+\phi_{12}=Mi_1+L_2i_2$$
- la regola della mano dx lega il verso positivo del flusso ed il verso positivo della corrente
- da faraday posso ricavare le tensioni, note le correnti o i flussi magnetici
