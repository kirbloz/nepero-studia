Application Specific Integrated Circuit: sono dei circuiti integrati creati appositamente per risolvere un problema elettronico specifico.
La progettazione e implementazione è fine SOLO e SOLAMENTE all'impiego predefinito.

Sono però *molto costosi*, dunque si sfruttano solo se possono essere impiegati in volumi massicci, altrimenti non è worth-it (es. elettronica di consumo).

Di solito prima di realizzare fisicamente un ASIC si progetta tutto sfruttando le FPGA (riprogrammabili), ma le FPGA sostituisono le ASIC nel caso in cui i volumi non ne permettano la produzione.

![[Pasted image 20231201145357.png]]

## Pro e Contro
Facciamo un comparison rispetto alle tecnologie FPGA/CPLD

*Vantaggi*
- Riduzione dei costi diretti (una volta sviluppato e già progettato)
- Migliori prestazioni, è un HW progettato ad-hoc
- Compattezza (integra più porte e funzioni)
- Tecnologia mista (analogica e digitale su uno stesso chip)

*Svantaggi*
- Elevati costi di sviluppo (milioni)
- Elevati tempi di sviluppo (sopra 3 mesi)
- Poco adatto a medio-bassi volumi (non worth it economicamente)
- Minore flessibilità; è intrinsecamente NON riprogrammabile


## Livello di descrizione
![[Pasted image 20231203101127.png]]

Partendo dal basso esistono diverse modalità per descrivere/progettare un dispositivo digitale. Dipende molto dalla complessità del prodotto finale.

1. **MASK**: descrive il layout fisico del circuito intergrato; serve a specificare gli strati per la produzione a livello transistor.

2. **GATE**: si descrivono componenti a basso livello e le reti di connessione; ad esempio per il 22v10 abbiamo progettato la mappa di memoria a GATE

3. **RTL**: o Register Transfer Level; si specificano i componenti complessi e la loro interconnessione; è qui che si evincono i limiti della temporizzazione.
	>Ad esempio quando si progetta un piccolo processore, una periferica o un microcontrollore, è meglio descriverlo utilizzando blocchetti funzionali tipo contatori, memorie etc. Se usassi i singoli Gate farei meglio a spararmi prima
	
4. **COMPORTAMENTALE**: descrivo sfruttando le funzioni da implementare; elenco i tempi, l'area di silicio e la dissipazione di calore/potenza.
   Questa descrizione rimane sempre e comunque *indipendente* dall'implementazione.
   >Per i SoC non posso descrivere un'intera interfaccia WiFi scrivendo i singoli sommatori e comparatori; mi limito a disegnare un coso che rappresenta il modulo WiFi e tengo conto delle caratteristiche in termini di consumo, area di silicio e tempo di propagazione.

---

## Progettazione e Realizzazione
Vedi [[Logica Programmazione#FPGA e ASIC - Tecniche di programmazione]].
