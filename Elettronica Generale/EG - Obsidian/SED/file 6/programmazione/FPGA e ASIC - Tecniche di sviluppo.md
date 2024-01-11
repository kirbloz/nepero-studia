~~Siccome FPGA nasce come il modello prototipale di ASIC, ad alto livello vengono descritti nella stessa maniera. A partire dagli anni 80 però anche FPGA ottiene un suo mercato.~~

Riporto il flusso di progetto:
![[Pasted image 20231203104136.png]]

### Modello Comportamentale
Il progetto viene descritto a *livello comportamentale* (più alto) mediante linguaggi procedurali orientati alla descrizione di circuiti (HDL).
Per lo standard del 1987 a cui ci atteniamo noi, vale il linguaggio VHDL. Inoltre per lo sviluppo di applicazioni speciali si fa uso di diversi e speciali formalismi appositi.

### Sintesi ad alto livello
La sintesi ad alto livello si occupa della *allocazione funzionale*.
>Se ci sono tante operazioni di somma, si prevede un sommatore (se si possono sequenziare) o più di uno (se si possono parallelizzare)

Si occupa anche dell'*implementazione funzionale*. 
>Ad un sommatore associo un'architettura ripple-carry piuttosto che carry look-ahead!

### Sintesi Logica
Nel realizzare la descrizione a *livello gate* si parte dalla descrizione *RTL*, che fornisce librerie di "strutture a gate" (blocchi di gate facili da usare!).

- E' qui che si fa la ricerca della FPGA più opportuna per realizzare il progetto: il discriminante è capire quale Mcell ottimizza al meglio le nostre richieste.

### Verifica del progetto
Per questa fase sono essenziali i simulatori, perchè permettono di svolgere un lavoro di *proofing* più rapido ed efficace.

- Purtroppo il modello di timing con ritardo variabili dell'FPGA rende questa fase *difficile*!

Gli step che si attraversano sono:
1. <span style="background:#40a9ff">Design Verification</span>: simulazione ad alto livello o pre-sintesi
2. <span style="background:#40a9ff">Implementation Verification</span>: simulazione a livello di gate o post-sintesi (PLD) o a livello layout (ASIC)
3. <span style="background:#40a9ff">Manufactoring Verification</span>: verifica del funzionamento corretto del prototipo

### Sintesi Fisica
Una volta che tutte le verifiche sono state superate, è tempo di mettere assieme i pezzi.

DEF :
 La *sintesi fisica* è l'insieme dei processi tecnologici che portano alla realizzazione fisica del circuito integrato.

NB: La produzione delle maschere per i processi di fabbricazione degli strati di silicio del IC richiede sofisticate tecniche, atte alla minimizzazione dell'area di estensione, i ritardi di propagazione, e la dissipazione della potenza!
