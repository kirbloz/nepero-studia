[[UNIVERSITA/CIRCUITI ED ELETTRONICA/FE/file 4/Comparatore]] con reazione positiva realizzata in questa maniera.

#### Configurazione
>DEF: la **reazione positiva** è un percorso realizzato tra l'uscita e l'ingresso $V_{+}$ dell'AO stesso.

>Riprendendo dallo schema di comparatore, dove si vuole che V_+ sia V_in e V_- sia GROUND: il V_in che si dà è V_out stesso.

##### Funzionamento reazione positiva
Se ho $V_{+}>V_{-}$ o $V_{in}> 0$ allora $V_{out}>0$ e dunque va ad aumentare il potenziale al morsetto positivo.
Aumentando $V_+$ questa si allontana da $V_{-}$ per cui più i due sono sbilanciati e più la reazione positiva li allontana l'uno dall'altro.
![[Pasted image 20231025001738.png]]
#### Caratteristiche: come variano


#### Segnali in uscita
Comportamento codifica OUT:
$V_{+} > V_{-}$ , cioè $V_{in} > 0$                   allora $+V_p$
$V_{+} < V_{-}$ , cioè $V_{in} < 0$                   allora $-V_p$


#### Perchè l'isteresi?
Perchè mi aiuta ad evitare il problema del rumore:

Immagino di utilizzare un AO classico configurato come comparatore. 
Fornisco un segnale in ingresso $V_{in}$ che sia una sinusoide al morsetto positivo; e collego il morsetto negativo alla massa così da non avere offset nel segnale.

Pongo dunque:$$\begin{align} V_{+} =& V_{in} \\ V_{-} \sim 0 =& \, \text{GND} \end{align}$$
Si modellizza l'ingresso $V_{in}$ come un generatore di tensione AC. 
Ogni generatore è soggetto al *fenomeno del rumore elettromagnetico*, quindi immagino che l'ingresso all'AO sia sempre determinato con $\pm 100 \text{mV}$.

Questa è la situazione:
![[001.png]]

MODIFICO IL MODELLO PER INTRODURRE QUESTO CONCETTO DI "SOGLIA": RETROAZIONE POSITIVA:

![[002.png]]

![[Pasted image 20231025001513.png]]
