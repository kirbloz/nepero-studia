>I microcontrollori - MCU - posseggono dei *porti* di IO logico: ovvero una serie di pin fisici ma gestiti diversamente a livello logico. 
  Spieghiamo.
  Normalmente si configurano tutti come ingressi, ma possono essere programmati con specifica software ad agire come uscite.
  A livello fisico sono realizzati con *buffer 3-state*, inizializzati a Z, con un ricevitore in antiparallelo per comandarlo.

---

La General Purpose Input Output è un tipo di interfaccia utilizzata per collegare un sistema embedded con "qualcosa", per scambiare segnali con "qualcosa".
Sono dei punti di IO digitale.

![[Pasted image 20231208175219.png]]

L'idea alla base è questa:
- Ci sta un buffer 3-state con un segnale di attivazione, che fa cambiare tra lo stato *read* e *write* - input e output.
![[Pasted image 20231208174041.png]]
- Questo segnale si chiama *PIN_MODE* e detta il *modo* di utilizzo del pin.
	Chiaramente è opportuno abilitare un pin come uscita SE E SOLO SE questo è effettivamente un uscita altrimenti rischio dei comportamenti conflittuali imprevedibili.
	A questo fine esiste anche un segnale di *RESET* che forza lo stato in *read* - unico modo che non genera conflitto.
	>Dopo un RESET, si va a vedere il valore di PIN_MODE per configurare il pin:
	>- "0" sarà input
	>- "1" sarà output

---

**Come si usano i GPIO?**
Ha due fasi:
1. init(): Si configura ogni singolo pin, dicendo al sistema ogni pin a cosa cazzo è collegato.
   >Qui è dove riporta il reset: rimette in automatico tutto a ingressi, disabilitando ogni trasmettitore 3-state e transceiver.
2. run()

---
GPIO fa tante cose! ecco qui.
Idealmente si progettano resistenze di pull-up e pull-down programmabili ma siccome i sistemi embedded lavorano il logica attiva-bassa, si tende a realizzare solo quella di pull-up.
>"Normalmente leggo 1, se agisce il segnale leggo 0"

![[Pasted image 20231208175943.png]]
