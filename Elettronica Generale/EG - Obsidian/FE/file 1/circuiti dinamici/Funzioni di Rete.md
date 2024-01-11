Qui parliamo delle Funzioni di Rete[^1]

#### Intro
In generale, ogni contenuto informativo può essere rappresentato come forma d’onda funzione del tempo, dello spazio o altra variabile.
Ogni forma d’onda di interesse $x(t)$ può essere vista come la somma di sinusoidi a frequenze diverse che costituiscono il suo spettro $X(f)$.
La trasformata di Fourier è lo strumento matematico che permette di scomporre $x(t)$ nelle sinusoidi (le armoniche) che la compongono.

#### Risposta in frequenza
La [[Risposta in frequenza |risposta in frequenza]] di un circuito dinamico è la variazione del suo comportamento al variare della frequenza $\omega$ - di una generica sinusoide.

<span style="background:#fff88f">Nella teoria dei sistemi dinamici diciamo che la risposta in frequenza è la descrizione della sua uscita usando come variabile la frequenza $\omega$ anzichè il tempo.</span>
*Per questo si dice che siamo nel dominio della frequenza!*
- Se $\omega = 0$ allora siamo in DC (regime continuo)
- Se $\omega \neq 0$ allora siamo in AC (regime alternato)
	In particolare se vale $\omega \rightarrow \infty$ allora si sta lavorando a frequenze molto elevate.

In *regime lineare* la risposta in freuqenza caratterizza completamente il comportamento del circuito, con qualunque ingresso.
(Si calcola lo sprettro, si trova la risposta e si antitrasforma dal dominio della frequenza a quello del tempo)

#### Funzioni di rete
Sia dato un circuito in regime sinusoidale con frequenza $\omega$.
![[Pasted image 20231009174445.png]]
Questo significa che
INGRESSO: un solo generatore con fasore $V_{in}$
USCITA: una qualunque variabile circuitale, tipo $V_O$

Il circuito simbolico è resistivo e lineare quindi: $V_{O}= F(\omega) V_{in}$

**FUNZIONE DI RETE** :
	La funzione $F(\omega)$ che non dipende dal generatore (ingresso) - ma dalla frequenza $\omega$
	In generale: $F(\omega) = \frac{\text{Fasore risposta}}{\text{Fasore ingresso}}$

Ci sono 6 tipi di funzioni di rete, e le prime 4 di queste sono chiamate **funzioni di trasferimento**
<span style="background:#b1ffff">- Impedenza di trasferimento (ohm)</span>
<span style="background:#b1ffff">- Rapporto di trasferimento in corrente \ tensione (ampere \ volt)</span>
<span style="background:#b1ffff">- Ammettenza di trasferimento (siemens)</span>
- Impedenza di ingresso (ohm)
- Ammettenza di ingesso (siemens)

##### IMPORTANTE SULLE FUNZIONI DI RETE
NB. Ogni funzione di rete è *funzione razionale reale* nella variabile complessa $jw$
NB. Ogni funzione di rete si ottiene risolvendo un *sistema di equazioni lineari* con coefficienti $jw$ o $1/jw$ relativi ai *componenti dinamici*.
![[Pasted image 20231009175206.png]]

#### CALCOLO DELLA RISPOSTA IN FREQUENZA
![[Pasted image 20231009175254.png]]





[^1]: Dal PDF n3 di CEE