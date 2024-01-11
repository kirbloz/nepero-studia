>E' una configurazione di [[Amplificatore Operazionale]].

>I <span style="background:#d3f8b6">transistori in zona lineare</span> sono utilizzati come amplificatori.

>- Un amp. ideale di *tensione* ha elevata impedenza in ingresso e bassa impedenza di uscita.
>- Un amp. ideale di *tensione* è in grado di mantenere la tensione voluta scambiando qualsiasi corrente


Il modello circuitale è questo: 
![[Pasted image 20231025160206.png]]

Questo barbai viene utilizzato come adattatore di impedenza[^1].
Si configura realizzando un *cortocircuito* tra l'uscita $V_{out}$ ed il morsetto $V_{-}$ $\Rightarrow$ è sempre un percorso di retroazione negativa.

Si usa anche per isolare due zone del circuito, di solito due impedenze.

>Esempio:
>Sia dato un generatore di tensione a $10\text{V}$ con resistenza di uscita di $20\Omega$.
>Questo generatore dovrà pilotare un carico variabile da $100\Omega \div 1\text{k}\Omega$ facendo in modo che la tensione ai suoi capi sia $10\text{V}\pm5$%
>
>$V_{out} \equiv 10V \equiv V_{in}$

#### Caratteristiche
- Il *segnale in uscita* di tensione si calcola come:$$V_{out}= V_{-}= V_{+}= V_{in}$$

[^1]: Che cazzo vorrà dire. Ah si, che indipendentemente dal carico, questo eroga sempre una corrente sufficiente a mantenere una certa tensione.