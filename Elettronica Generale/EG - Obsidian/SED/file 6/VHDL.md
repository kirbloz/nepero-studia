Linguaggio per dispositivi digitali FPGA (credo boh).
File su VHDL gigaenorme.

### Storia del VHDL
All'inizio del 1980 c'è un programma USA chiamato VHSIC che progetta circuiti integrati complessi. 
Nel '87 si propone il VHDL allo standard IEEE.
Nel 1992 si aggiorna lo standard IEEE ad una *multi-value logic*.

Il VHDL rispetto ai metodi/linguaggi tradizionali, mostra i seguenti vantaggi:
- migliore documentazione
- simulazione più potente
- migliore descrizione del processo di sintesi
#### Multi Value Legend
![[Pasted image 20231203105424.png]]

## Progettazione
### Modalità di descrizione
#### Strutturale
Modalità *netlist* e *boolean equations*.
- NETLIST: rappresentazione testuale di un linguaggio grafico (fatto foto a lavagna siu)
- BOOLEAN EQUATIONS: uso AND, OR, XOR, praticamente un linguaggio a livello GATE.

#### Comportamentale
Modalità *concurrent statements* e *sequential statements*. Sono più "normali" di quelli strutturali.
Si distinguono perchè uno è sequenziale e l'altro concorrente (stesso tempo di uscita): sono diversi dal punto di vista della simulazione (devo simularli diversamente).

### Design Flow
p3 giga file
Il flusso ci fa capire l'interazione con l'ambiente di sviluppo.
Faccio modello alto livello => simulazione comportamentale
Poi sintesi => simulazione funzionale
Dopo l'implementazione ho una simulazione con ritardi accurati: è qui che mi accorgo della meta stabilità.

#### Sim comportamentale
Non ho temporizzazione. Serve a individuare il comportamento in sè, la correttezza dell'eleaborazione che si cerca di ottenere.
Si creano dei vettori di test, li si sottopone al sistema e si osservano i risultati.

#### Sintesi
E' diversa, più orientata al FITTING nella CPLD, mentre al ROUTING nella FPGA.
Dopo il fitting..

#### Sim funzionale
Non ho ancora i ritardi precisi, perchè non ho scelto il componente, ma mi faccio un'idea.

#### Implementazione
Qui ho i ritardi precisi, e osservo la meta stabilità.

---
L'assegnazione dei pin è l'ultimo step.
Con l'FPGA faccio programmazione SW Oriented (prima di collegare, faccio il programma e non il contrario).
All'inizio si faceva così:
- prendo il componente e lo programmo
- poi collego al circuito

Oggi  c'e un IN CIRCUIT PROGRAMMING, che mi permette prima di saldare il dispositivo e poi di programmarlo.

JTAG: interfaccia universale dei dispositivi

Un FPGA necessita di un bootloader, quindi firmware che permetta il facile caricamento del programma


## Modellizzazione 

### COMPORTAMENTALE
Ho degli ingressi, genero delle uscite. Devo descrivere come si comportano queste uscite in base agli ingressi.
Mi serve per programmare il componente - la sintesi - ma soprattutto per la simulazione.
Prima programmo poi vedo se effettivamente funziona.
La diagnostica si fa guardando il monitor seriale. => non c'è simulatore!!

E' opportuno avere un simulatore perchè così mi facilito la vita.
Esiste un sacco di codice vhdl gratis.

### STRUTTURALE
Mi permette di collegare i componenti: approccio più tradizionale.
Posso anche mixare l'approccio *comportamentale* e *strutturale* in un progetto VHDL.
	Quando prendo qualcosa da una libreria, prob mi viene fornito a livello strutturale, lo collego.
	Ad esempio mi viene dato un sommatore, e scelgo il più bellino per il mio progetto.


---

## Programmazione
Quando programmiamo con linguaggio booleano usiamo funzioni e pin. Anche in VHDL ci sono due unità:
- ENTITY (equazioni - SW)
- ARCHITECTURE (pin description - HW)
### Entity declaration
E' la matrice interfaccia dove indico nome e tipo di dato.

PORT DECLARATION: Mi permette di specificare i porti (pin) (Va sempre fatta)
GENERIC DECLARATION: Posso anche fare dichiarazioni generiche, ad esempio ci caccio le costanti

Nel port decl dichiaro dei segnali con *nome*, *modo*, *tipo*.
NOME: facile

TIPO: BIT, BYTE etc (vettore di bit), INT, FLOAT 
>Non è legato ai pin

*MODO*: ci sono quattro modi, IN, OUT, INOUT, BUFFER
- IN e OUT ok
- INOUT è bidirezionale
>INOUT si può usare con IN per bottone ma facendo attenzione a disabilitare il tristate sennò implode
>Può essere usato per applicare dall'esterno un valore forzante.
- BUFFER è un'uscita con feedback interno
>*E' un'uscita che posso rileggere*, ma non potrà mai entrare nulla dall'esterno

Prima il modo era fisso per il componente (vedi la 22v10) dove ha il PINOUT *fisso*. L'HW vincola e stabilisce il modo!
Un dispositivo generico non indica il modo, starà al progettista capire poi tramite fitting come collegare al meglio.
Nessuno ci chiede di definire il modo quando programmiamo, ma l'HW ha esisgenza di saperlo! ( a meno che lo indichi lui )

FOTO FATTA ALLA LAVAGNA DA INCOLLARE QUY

## Architecture
Ad un entity posso associare tante architecture.
ESEMPIO
Un sommatore 4 bit può fare triple carry o carry look ahead.
Un contatore a 8 bit può essere arch sincrona o asincrona con stadio di sincronizzazione finale.

Gli stili architetturali sono tipo
- strutturale
- misto
- un altro

Si possono dichiarare
- SIGNAL
- CONSTANT
- TYPE

## PUTTING IT ALL TOGETHER

p28 gigafile
Realizziamo 3 MUX uguali.
Come faccio l'entity? Guardo ingressi ed uscite, li chiamo ancora bit e tengo la lista di ste cose.

L'architettura? Descrivo ogni uscita.
*Simple signal assignment*: Tipo la X con tabella della verità: OR di due midterm.
*Conditional assignment*: WHEN ELSE e WITH SELECT. 


## Package
Insieme di coppie entity-architecture. Un insieme di oggetti. Alla base del concetto di libreria.
Non entreremo nello standard del package perche non ha utilità.
Alcuni li dichiariamo e li usiamo va be ma che sta dicendo che palle.
Una libreria contine 1+ package è dunque ad un livello superiore.

Lib STD è combinazione dei due package che esistono sempre. Definisce i tipi. BIT e BOOL.
Esiste anche la Lib IEEE: contiene tutta l'aritmetica necessaria agli standard logic, sono tdi tipo multilivello. 
Anche un'operazione semplice come l'AND, eh solleva dilemmi e dubbi. Questa roba ci da un'essenziale contributo nel conservare la nostra sanità mentale.
Gli operatori sono ben definiti sui BIT, sugli INT e FLOAT pota ti inculi.

### STD_LOGIC
Package standard logic nella libreria IEEE.

I livelli DEBOLI non sono supportati dalla sintesi p 35 (W, L, H): sono molto dipendenti dall'aver associato una cella di ingresso o uscita.
Sono poco gestiti, degli sfigati insomma. Li tocco solo quando la sintesi è già fatta e pronta ualà

Quando vedo X è un brutto segno, mi coppo.

### STD_ULOGIC
Unsigned Logic. 
La sottrazione nella aritmetica senza segno deve prevedere errore se vado sotto 0.

### Enumerati
TIpi enum

### Operatori VHDL
pagina 37
Di tipo
- logico
- relazionale
- somma e concatenazione
>prendo 3 bit e 3bit e li affianco e li considero cm una sola parola da 6bit
- segno
- moltiplicazione
- miscellanea

Overload OPERATORE
STD_LOGIC_VECTOR: p40 ci aggiungo un bit e outputto un std logic vector piu lungo

### Assegnazioni dei segnali
SOno concorrenti e seuqenziali
quelli concorrenti sono
- simple: <= il piu semplice
- conditional: nome WHEN condizione ELSE nome WHEN etc
  questa selezione implicita implica un'HW di MUX: praticamente sto istanziando le porte. p47
- selected: si basa su MUX ma concorrente, cioè sel immagino sia un vector due bit. 
  UN UNICO MUX CHE RAGGRUPPA TUTTI I CASI POSSIBILI

da un pov funzionale, conditional e selected sono tipo uguali, vengo dalla stessa tabella della verità.
In una logica estesa sono diversi! e anche con schema di temporizzazione, (conditional ha ritardo)