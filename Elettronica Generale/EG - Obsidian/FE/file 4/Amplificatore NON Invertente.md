E' una configurazione variante dell'[[Amplificatore Invertente]] che permette di mantenere inalterato il segno dell'ingresso.
Si chiama Amplificatore invertente di Tensione, e si realizza configurando l'AO con una variante della reazione negativa. Di seguito uno schema del circuito:
![[Pasted image 20231025154648.png]]

#### Configurazione
>DEF: la **reazione negativa** è un percorso realizzato tra l'uscita $V_{out}$ e l'ingresso $V_{-}$ dell'AO stesso.

La presenza di $R_{2}$ abbassa la tensione nel punto dove si legge $V_{out}$ 
$\Rightarrow$ la corrente in uscita attraversa TUTTA $R_2$ e poi va verso massa attraverso $R_1$. Solo una piccola corrente di perdita torna indietro, sempre nell'ordine dei pico Ampere.

Per il funzionamento della reazione negativa vedi [[Amplificatore Invertente#Funzionamento reazione negativa]]. 

#### Caratteristiche
- Il *segnale in uscita* si calcola come: $$ V_{out}=V_{s} \,\cdot\, (1+ \frac{R_2}{R_1})$$

- Il **guadagno** è sempre $>1$; più $R_{2}>>R_{1}$ e più amplifico la tensione. Sempre nei limiti della regione lineare. ( * )

- Non entra corrente nei terminali di ingresso; come in ogni AO $I_{+}= I_{-} \sim 0$
- C'è retroazione negativa:$$ V_{+}= V_{-} = V_{s} \quad \quad V_{id}=0$$
--- 
Dalla legge del partitore posso dire che $$V_{-}= V_{s}= V_{out}\,\cdot\,\frac{R_1}{(R_{2}+R_{1})}$$
Esplicitando rispetto a $V_{out}$ si ottiene: $$ V_{out}=V_{s}\,\cdot\, \frac{(R_{2}+R_{1})}{R_{1}} = V_{s}\,\cdot\,(1+ \frac{R_{2}}{R_{1}})$$



( * ) NOTA BENE: il comparatore con isteresi e l'amplificatore non invertente sono molto simili; cambia la polarità di retroazione.

Ottimo da usare per amplificare segnali scrausi da un sensore molto economico.