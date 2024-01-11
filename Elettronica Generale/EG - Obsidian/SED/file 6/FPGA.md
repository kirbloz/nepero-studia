Le [[FPGA]] sono la tecnologia ad oggi più diffusa e sfruttata perchè ha come caratteristica principale la *RETE di canali di comunicazione* tra celle logiche, che le rende appunto, riprogrammabili.

Sono delle schede ad alta capacità ed elevata flessibilità anche se prototipali e volatili (RAM).
Funzionano scaricando il programma su di una memoria in scheda.
Oggi usate nei Soft Processor nelle DSP.
Esistono le *Mixed Signals FPGA*, che integrano ADC e DAC, sono [[System-On-a-Chip|SOC]].
Possono integrare anche altri processori evoluti o altri circuiti.
>Nascono principalmente per realizzare prototipi, anche complessi ([[ASIC]])

---
## Tecnologia
Le FPGA evolvono dall'architettura CPLD e la rendono più complessa ma anche più flessibile.

Introducono una *matrice di Mcells* con *griglia di connessioni*.
- Le uscite sono <span style="background:#affad1">funzioni</span> descrivibili in modo del tutto generale
- Il <span style="background:#affad1">tempo di propagazione</span> da IN a OUT dipende dal tipo di *strategia di connessione* delle *sottofunzioni elementari*

![[Pasted image 20231202190332.png]]

## Caratteristiche
Le caratteristiche principali sono:
- Elevato numero di *Mcells* o blocchi logici (sia IO che interne)
- La *matrice di interconessioni distribuita*. 

Nelle CPLD questa matrice era fissa! Il software doveva occuparsi del **fitting** per calzare al meglio le caratteristiche del dispositivo fisico. 
Ad esempio il programmatore doveva conoscere la tecnica di allocazione dei PTERM per poterli sfruttare al meglio e senza sprecarli. In ogni caso si consumava come se si usasse il 100% della capacità.

Ora il programmatore delle FPGA sà che il software compilatore si occupa del **routing** (roba difficile) per capire come far comunicare al meglio le macrocelle (delivery dei segnali).
Insorge un problema:
- Problema del ritardo di propagazione, si introduce un DISALLINEAMENTO TEMPORALE VARIABILE. Dipende da come il routing per quell'elaborazione viene svolto!
- E' anche difficile emulare le FPGA proprio perchè il ritardo è variabile sul collegamento.
>Nelle CPLD si dice che il ritardo è dominante, dunque nullo.

### Blocco logico
Sempre quello è. Dalla GAL alla CPLD al FPGA. Ovviamente continua a svilupparsi.

- In questo caso ha due FF, è più grossa per risparmiare connessioni.
- Architettura complessivamente molto flessibile, simile a due Mcells unite
- Non siamo vincolati ad una sola tabella della verità, ma avendo funzioni di funzioni anche interne è possibile concatenare più tabelle

### Interconnessioni
Il **problema** non è realizzare il blocco logico (che sia con LUT o tramite SoP+FF). Per l'FPGA il grosso dello sforzo finisce nella progettazione delle interconnesioni.

![[Pasted image 20231202192325.png]]
![[Pasted image 20231202192015.png]]

Le matrici di interconnessione in realtà non sono fusibili, sono transistor!
Tutti i possibili collegamenti sono presenti fisicamente, ma non tutti sono compatibili (ovvero non tutti si possono attivare in contemporanea ad altri)
>Questa matrice è stata ispirata dal paradigma ferroviario. Permette di affaticare le PSM il meno possibile.

### Circuiti Ricorrenti
Le FPGA sono realizzate usando Mcells diverse e PSM diverse. Dunque esisono FPGA specializzate in certi compiti piuttosto che in altri.

Per questo stesso motivo le FPGA contengono *circuiti ricorrenti cablati*, hardware dedicato e specifico, ad alte prestazioni!
>Se il mio progetto non usa moltiplicatori, sarà poco saggio utilizzare FPGA con circuiteria dedicata a moltiplicare!



