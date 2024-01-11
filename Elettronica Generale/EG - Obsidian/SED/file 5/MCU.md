Il microcontrollore montato sui sistemi embedded.
Tipicamente sono dei derivati dell'8051 molto semplici oppure ARM. 

Per far funzionare un microcontrollore servono 3 elementi:
1. sistema di alimentazione/massa
2. clock 
3. reset

*Nota*: il reset è FONDAMENTALE!
Il MCU potrebbe ricevere segnali anomali e sbabbiare e perdere il controllo.. il segnale di RESET mi permette di riportare tutto ad una configurazione nota e tranquilla.

---

## Processore
Sono a 8-16-32 bit, ad aritmetica intera, sommatori HW, moltiplicatori firmware. Arduino ha in più di queste caratteristiche, diversi operatori dedicati ai sensori (misurare $T_{w}$ o il tempo o lo sfasamento..)

*NB*: NON HANNO SISTEMA OPERATIVO!
Sono solo dei compilatori C.

## Memorie
Sono di solito:
- *flash* per poterci caricare ed eseguire il codice.
- *SRAM* per memorizzare i dati.
- *Serial Flash* o *EEPROM* per la configurazione.

## Periferiche e pin IO
Ciascun pin fisico del sistema può essere configurato in uno dei seguenti modi.

### IO
1. I microcontrollori - MCU - posseggono dei *porti* di IO logico. Vedi [[GPIO]].
### Temporizzazione
2. La temporizzazione è compito di un'unità dedicata: *timer free-running*, praticamente dei contatori per scandire il tempo. 
	Contengono anche registri che memorizzano istanti di eventi: ad esempio un fronte di salita, o il momento in cui commuta una certa uscita.
- Si occupa delle uscite PWM
Vedi [[Timing Processing Unit]]
### Periferiche
3. [[Interfacce Seriali]]
4. *Convertitori AD*, che gestiscono come dei multiplexer pià ingressi. 
   >Ad esempio approssimazioni, 10 bit etc..
5. [[Interfacce USB]]

---
