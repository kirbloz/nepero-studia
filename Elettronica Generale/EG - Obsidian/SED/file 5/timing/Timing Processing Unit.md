Nei microcontrollori esiste quasi sempre un'interfaccia seriale, e quindi esiste sempre anche un clock per la generazione dello stream di bit e il campionamento.
>La frequenza di questo clock è programmabile! (diversi baudrate)

Quindi nei MCU esiste sempre un clock a frequenza programmabile ottenuto da:
- *timer free running*, o contatore a $n \ge 16$ bits azionato dal clock di sistema
- sistema di *prescaler*, un multiplexer che seleziona una tra le $n$ linee di uscita del contatore (divide la frequenza)
Tutta sta roba rappresenta la Timing Processing Unit integrata in un MCU.

---
## Timer Free Running
DEF : il *timer free running*
 è un contatore a $n$ bit alla frequenza di clock che sia la massima operativa del MCU stesso.
 Permette una gestione del tempo *relativo* - tra un evento e l'altro - ma non di quello *assoluto* - giorni, ora, minuti.
![[Pasted image 20231209095750.png]]

- Può essere letto e viene resettato dal reset comune con il MCU.
![[Pasted image 20231209003703.png]]

#### Real-Time Calendar
Alcuni PC molto vecchi, se si spengono, si resettano a 01/01/1970. 
I PC più nuovi invece sono dotati di una batteria miniaturizzata che permette al PC di contare il *tempo assoluto*.
- La precisione suprema la si raggiunge quando esiste un'infrastruttura che si collega alla rete per cui il dispositivo ottiene informazioni legate alla zona (ora legale, fuso orario..)

#### Utilità FRT
In sostanza il free-running timer è utile solo se il sistema è sconnesso dal mondo. In caso contrario si sa il NTP - Network Time Protocolo - per interrogare dei server pool sul tempo assoluto.

Ma una cosa essenziale la fa comunque! Il TFR permette di memorizzare il "momento" in cui avviene un certo evento.. per cui permette di eseguire calcoli come questo:
![[Pasted image 20231209100257.png]]

Un esempio può essere la *generazione di delay*.
Potrei necessitare di una funzione che prevede di generare un segnale ad onda quadra così:
"1" - sleep 1ms - "0" - sleep 1ms - "1" - ..
![[Pasted image 20231209100855.png]]

Funzione **sleep**:
Immagino di voler attendere 1ms
![[Pasted image 20231209100953.png]]
Ricalcolo ad ogni fronte il tempo trascorso dal momento di inizio dell'attesa.


*Nota*: calcolare il tempo trascorso - o la *durata* di qualcosa serve in tanti contesti.
Però per avere che questo calcolo sia efficace è necessario che il timer free-runnning integri un contatore con TANTI bit!
E' terribile se va in overflow!
>Di solito $\ge 16$ bits.

---
## Timing Processing Unit
Nella TMU troviamo diversi componenti.

>Il PRS è il Peripheral Reflex System ovvero l'insieme di periferiche che comunicano senza passare dall'MCU. Utile per evitare che le funzioni bloccanti del timer blocchino anche il processore.
![[Pasted image 20231209004247.png]]
### Timer/Counter
I timer nei microcontrollori sono dei *contatori alimentati da un clock legato al clock $F_{ck}$ di funzionamento della ALU* 
>Possono esister più di un timer/counter in un MCU

- I Timer/Counter possono essere free-running o attivati e fermati su comando

### IC - Input Capture
La Input Capture, come suggerisce il nome, *cattura* il valore del Counter (Timer Free Running -TFR) in corrispondenza di un evento esterno (es. fronte di un segnale di ingresso).
>Cioè legge in quale momento si verifica un certo evento

Vedi [[TMU - Hardware di cattura]]

### OC - Output Compare 
La Output Compare si occupa di *generare* un evento quando il TFR (il counter) raggiunge un certo valore in precedenza specificato. L’evento generato può essere relativo ad un segnale di uscita o ad altre periferiche (Seriale, ADC,..).
>Cioè segnala che è passato un tot di tempo/è arrivato un momento atteso.

- il calcolo del PWM è un caso di OC
Vedi [[TMU - Hardware comparatore]]
---
## Comandi bloccanti
Esistono delle funzioni che possono usare le periferiche e che sono in grado di "bloccare" la MCU: occupano la TPU perchè in attesa di certi ingressi speciali.
Si chiamano *attività che bloccano le altre routine del timer*, ed è il costruttore della periferiche a realizzare la funzione che si usa per interrogare la TPU.

Cosa succede effettivamente durante sta attività di loop bloccante?
- $T_{FR_{i}}$ attende certi ingressi (OC).. Per ipotesi:
	- IN="1"? se sì memorizzo $T_{FR_A}$ leggendo il timer; altrimenti aspetto
	- Ho letto $T_{FR_A}$ e ora aspetto un IN="0"; se sì memorizzo $T_{FR_B}$ altrimenti aspetto di nuovo
- Ora ho tutti i dati per calcolare:
 ![[Pasted image 20231209102246.png]]

*Nota*: questo semplice loop per il calcolo del tempo tra due eventi mi ha bloccato il timer PER TUTTA LA DURATA DI QUESTO TEMPO!
A livello SW mi genera del ritardo.. E' quindi opportuno sfruttare la TPU (dedicata) hardware per poter calcolare in maniera indipendente e senza implicare attese scomode.

