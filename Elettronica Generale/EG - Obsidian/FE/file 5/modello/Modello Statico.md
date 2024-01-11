Vediamo un modello comportamentale semplificato.

## Logica Binaria
La <span style="background:#fff88f">logica binaria</span>, come introdotto in [[Codifica Binaria]], tratta un trasferimento di informazioni: il modello comportamentale è  una tabella di verità (LookUp Table, LUT).
![[Pasted image 20231031221745.png]]
Questo è a grandi linee. Facciamo delle osservazioni al modello "scatola":

- In realtà in ingresso non abbiamo delle _informazioni_, abbiamo dei _segnali elettrici_, che sono caratterizzati da **tensione** e **corrente**.
- 
- In uscita andranno collegati altri dispositivi logici, altre funzioni F,G,H che siano. Come caratterizzo l'uscita di conseguenza? Se le entrate sono segnali elettrici, allora anche le uscite (che poi diventano entrate) dovranno esserlo.

<span style="background:#fdbfff">E' necessario tradurre, codificare, introdurre un'area di passaggio da segnale elettrico a informazione.</span>

---
## Elettronica Digitale
L'<span style="background:#fff88f">elettronica digitale</span> tratta un trasferimento di segnali elettrici per cui un modello comportamentale accurato è più complesso. Introduciamo degli stadi di interfacciamento con il mondo esterno.

*Nota*: gli stadi PRE e POST elaborazione servono per la compatibilità dei dispositivi di elaborazione.
### Stadio IN e OUT
![[Pasted image 20231031222639.png]]
Questo è un modello più "veritiero".
Commento: [[Ritardo di propagazione]]
![[UNIVERSITA/CIRCUITI ED ELETTRONICA/SED/imgs/Pasted image 20231031223206.png]]

Per degli esempi di implementazione di logica vedi [[Modello - Interruttori]]

### Modello circuitale - Interruttori
Come si realizzano gli stadi di uscita e di ingresso a livello circuitale? Come si codifica?
Vedi [[Modello - Circuito]].
Qualcosa che mi piace è la capacità di [[Rigenerazione del Segnale]], ovvero l'attitudine di un dispositivo a buttare fuori segnali più "belli".
### Codifica - Livelli di tensione
Facendo riferimento a [[Codifica Binaria#Convenzioni]]
![[Pasted image 20231031232809.png]]

### Parametri statici di interfacciamento
Queste sono caratteristiche tecnologiche, dovute al fatto che questi dispositivi lavorano con segnali elettrici.
I segnali elettrici sono caratterizzati sia da *corrente* che da *tensione* quindi sono necessarie due proprietà che dettino regole su entrambe.
Vedi [[Immunità al rumore]]
Vedi [[Fan-Out Statico]]

### Modello dinamico semplificato
Commento sul [[Ritardo di propagazione]].
I ritardi si modellizzano con condensatori la cui carica e scarica produce ritardo.
Da: $V = Q/C$ e $I=dQ/dt$ 
Piccole correnti caricano lentamente il condensatore
Nei circuiti equivalenti RC, elevate resistenze caricano lentamente il condensatore (tau!)