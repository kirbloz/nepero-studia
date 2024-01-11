Detto Serial Peripheral Interface.
Prevede 3 segnali principali indispensabili, più un extra.
- *MOSI*, master outp - slave inp.
	E' la linea che manda i dati da M a S, quindi di *write*

- *MISO*, master inp - slave outp.
	E' la linea che manda dati da S a M, quindi di *read*.

- *SCK*, serial clock.
	E' il segnale di clock condiviso tra M ed S.

---
Qui una classica configurazione di comunicazione Master-Slave:

![[Pasted image 20231209001157.png]]
![[Pasted image 20231209001217.png]]

### Collegamento parallelo
Moltissimi dispositivi usano lo [[SPI]], ma come si può ottimizzare l'HW?
  Un modo può essere collegare in *parallelo* tanti slaves e poi prevedere una linea SLAVE_SELECT per decidere con il master dialogherà
  Questa cosa è ottima, ma mi fa perdere tanto tempo.
  >Si può far parlare con UN SOLO slave alla volte! Il mezzo non ha multiplazione.
  
*Nota*: il processo di scelta dello slave è "HW device selection" => un meccanismo *hardware*. Servono $n$ linee con $n$ slave per poter implementare questa logica!
Quello che questo segnale fa è attivare lo slave solo sul traffico di sua pertinenza
>Cioè io mando a 3, attivo SLAVE_SELECT=3 così il 2 non ascolta, ma il 3 sì!

![[Pasted image 20231209001143.png]]

### Collegamento chain
Un modo ulteriore per ottimizzare il parallelo è la *chain connection*: praticamente una serie di collegamenti.

Osserva l'immagine.
La <span style="background:#affad1">linea verde</span> collega sempre e solo due diversi dispositivi. Il pin MOSI è in grado di agire come MUX (inoltra o accetta pacchetto): questo pin può disattivare lo SHIFT-REGISTER (accetta) e comportarsi come un BUFFER (inoltro), ributtando sull'uscita MISO.
- Tutte le domande master->slave attraversano tutta la catena

La <span style="background:#b1ffff">linea blu</span> rappresenta le risposte, che da qualunque slave partano, dovranno sempre uscire dall'ultimo perchè richiude la catena con il master iniziata dal pin MOSI.
Le risposte quindi arrivano tutte a cazzum e il master sa da chi arriva sia perchè di solito il singolo slave "si firma" nel pacchetto, ma perchè con la SLAVE_SELECT impone di parlare con UN SOLO SLAVE PRECISO alla volta. 

*Nota*: il processo di scelta dello slave è "SW device selection" => un meccanismo *software*. Servono $n$ linee con $n$ slave per poter implementare questa logica!
Questo segnale invece fa in modo che lo slave si attivi SEMPRE (ad ogni ricezione) e legga l'indirizzo nel pacchetto inviato: come un router accetta se l'indirizzo destinatario è sè stesso, altrimenti inoltra.

![[Pasted image 20231209001903.png]]


---
## I^2C

Inte-Integrated Circuit.

Altre ottimizzazioni SPI sono
- i^2C: una sola linea di dati bidirezionale + una linea di clock
- FULL DUPLEX: due linee una MISO e una MOSI

Quando c'è una sola linea (mezzo) per parlare, slave e master devono per forza parlare alternati. E' scomodo, lento e difficile da regolare però è *economico* in termini di pin e canali fisici