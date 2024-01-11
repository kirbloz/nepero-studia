I transistori in zona di saturazione e interdizione sono utilizzati, rispettivamente, come interruttori accesi e spenti.

**Spento** (aperto) :
 Un transistore in zona di interdizione (e nella limitrofa zona attiva) ha una corrente *di collettore* $i_{C}$ molto piccola e quindi si comporta come una resistenza di valore molto elevato.

**Acceso** (chiuso) :
 Un transistore in zona di saturazione (e nella limitrofa zona attiva) ha una corrente *di collettore* $i_{C}$ molto grande e quindi si comporta come una resistenza di valore molto basso.


NOTA: è con gli interruttori che si realizzano le funzioni di logica digitale.

---
#### Tecnologie

##### Bipolare npn
Equivale ad un interruttore che si chiude e fa passare $I_c$ se si applica $Vbe>0.6V$.

- Elevate correnti in gioco
	- <span style="background:#affad1">Potente e veloce</span>
	- Dissipazione, <span style="background:#ff4d4f">consuma molto</span>
- Necessita di<span style="background:#ff4d4f"> resistenze ingombranti</span> per il controllo delle correnti
- Ha una <span style="background:#affad1">tensione di uscita non nulla anche "a vuoto"</span>, $V_{\text{ce, sat}}=0.3V$
##### nMOS arricchimento
Equivale ad un interruttore che si chiude e fa passare $I_d$ se si applica $V_{gs}>1V$ 

- Ha <span style="background:#affad1">regione ohmica</span> => agisce come resistenza. Non servono da se.
- <span style="background:#affad1">Non richiede corrente in ingresso</span>
- <span style="background:#affad1">Non ha tensione di uscita "a vuoto"</span> ($V_{ds}=0V$)
- <span style="background:#ff4d4f">capacità in ingresso </span>(ritardo sul comando)

---

### Diodo
Anche il diodo è un interruttore: però *non ha un comando*.
Non prevede nessun morsetto a cui trasmette segnale di switch! 
Non è un tripolo ma un bipolo, e il suo comportamento dipende dalla tensione ai suoi due poli.
Applico un $V$ -> scorre una corrente $I$ seguendo questa legge:
$$\large I= I_{o}(e ^{V /nVt}-1)$$
- La tensione di attivazione dipende anche dalla temperatura del componente
- La corrente di base $I_o$ è nell'ordine di $nA$ e viene amplificata fino a $mA$ quando è in conduzione

Vedi [[Famiglie Logiche]] per vedere come i diodi ~~non~~ vengono utilizzati nel realizzare funzioni logiche.

#### Modello Semplificato
Noi semplifichiamo così:
![[Pasted image 20231101172513.png]]
La tensione di attivazione: $V_{s}\sim 0.7V$

Per $V<V_s$          APERTO: $I \sim I_{o}\sim nA$            $I=0$
Per $V>V_s$          CHIUSO: $I \sim mA$                   $I= (V-V_{s})/R_{d}$ 

Siccome il diodo in conduzione si comporta come un generatore reale, modellizziamo una resistenza $R_d$ interna.

