Si chiamano Complex PLD, seguono le GAL (ultima innovazione delle SPLD). 

DEF :
 le *macrocelle interne* sono MaC non collegate a pin di uscita.
DEF :
 ogni *uscita* è una funzione descrivibile come una connessione di SoP con possibilità di FF.

Per questo motivo la CPLD condivide i *pterms* centrali, lasciando l'allocazione esclusiva solo a quelli periferici.

### Temporizzazione
Il tempo di propagazione da ingresso a uscita ha modelizzazione semplice poichè il ritardo non dipende dal tipo di funzione ma dal numero di volte per cui si passa dalla matrice.

>Questo perchè è come prendere tante 22v10 e collegarle tra loro, per cui si mantiene la caratteristica della temporizzazione bella. 

## Tecnologia
>Dalle GAL alle CPLD: minuto 4.18 del video 12/07

Si realizzano architetture diverse ed un po' più complesse: per fare funzioni è più complesse bisognava spezzarle in tante SoP e poi ricomporle. Dispendioso!

- Idea: realizzo una macrocella per pin e non solo per uscita: 24 pin -> 24 MaC. Oppure aumento i piedini!
- Idea passima.. svincolo le MaC ai piedini, MaC di appoggio.

**"Realizzare macrocelle interne e comuni a più pin"**
Questa idea deriva dal fatto che è inutile vincolare un MaC ad un pin solo perchè tanto poi se quello calcolato è solo un minterm, non ha senso che esca dall'architettura: l'elaborazione non è completa!
![[Pasted image 20231202121000.png]]

- Collegare le MaC interne  a linee di feedback è un problema perchè aumentano le connessioni e si viola il fan-in delle porte OR.
Creo la *matrice delle interconnessioni*, che anda delle linee in select tra AND e OR per rispettare il fan-in.

### Nota
Dove realizzo le funzioni più complicate?
Al di fuori! Perchè così dispongo di OR, che stanno all'esterno e hanno accesso a tanti *pterms*.

### Blocco logico
I blocchi logici sono alla base dell'architettura CPLD. Sono fatti così:
![[Pasted image 20231202160109.png]]

#### Product Term Array = matrice AND
I pterms vengono raggruppati per cui ogni porta OR comprende da 0 a 16 pterms.
Questa matrice si connette direttamente a quelle delle interconnessioni attraverso delle linee di select.

#### Product Term Distributor = matrice OR
Per ogni OR, per ogni macrocella, arriverranno più pterms, ma in maniera da ottimizzare il fan-in.

In questo schema, per ogni macrocella ci sono da 0 a 16 pterms.
Quelle centrali hanno molta condivisione, ovvero vedono pterms in comune a tante mcells. Dunque con l'architettura CPLD si torna ad avere i pin esterni forti (funzioni più complesse).
![[Pasted image 20231202170046.png]]

**CENTRAL SHARING** :

**PERIPHERAL STEERING** :

#### Mcells
La MaC può essre di IO oppure buried (già interfacciata all'uscita, oppure interfaccia di nuovo alla matrice delle interconnessioni).

- Nella GAL ricordiamo che il primo PIN era dedicato al clock, per poter adattare alta frequenza, alto carico capacitivo, alimentazione sufficiente per tutte le celle (fan-out).
Ora internamente possiamo realizzare sistemi di rigenerazione del segnale, per cui abbiamo più flessibilità.
---
**TIMING**:
Come funziona il timing per le Mcells di ingresso del CPLD?
- Anche la CPLD è sprecona in termini di fusibili (se realizzo funzioni semplici spreco gran parte delle risorse)
Ha una temporizzazione bestiale e un ambiente di sviluppo praticamente a gratis

Altra osservazione, si nota che all'ingresso dei segnali di clock ci sono poi due flip-flip in cascata: sono necessari per avere un *filtro alla meta-stabilità*!

---

>NB: raggruppare tante linee in una porta è uno schema funzionale. Perchè in realtà non esistono AND ciccione abbastanza da avere 44 input.. per cui la matrice AND divenza una selezione programmabile delle colonne (input)
![[Pasted image 20231202171223.png]]
### Schema di una Mcell
Immagine non da sapere a memoria nè leggere particolarmente. 
![[Pasted image 20231202170352.png]]

PTM : pterm


## Limiti


