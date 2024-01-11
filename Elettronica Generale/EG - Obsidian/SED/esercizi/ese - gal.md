
## Pinout
22 piedini + 2 gnd / Vcc

PIN 1: clock
PIN 12: gnd
PIN 24: Vcc
PIN 13: nc

### LOAD


**Load Sincrono**
![[Pasted image 20231202154527.png]]

$$OUT = OUT_{logic}\,\, \cdot \,\, \overline  {LOAD} \,\,+ \,\, D_{i}\,\, \cdot \,\, LOAD$$
LOAD = 0 => calcola l'uscita
LOAD = 1 => pone in uscita i dati in entrata

### ENABLE


$$OUT = OUT_{logic}\,\, \cdot \,\,  {EN} \,\,+ \,\, OUT\,\, \cdot \,\, \overline {EN}$$
EN = 0 => mantiene lo stato corrente/vecchio
EN = 1 => calcola l'uscita

### DIREZIONE


![[Pasted image 20231202154545.png]]

## Metastabilità

I segnali soggetti a metastabilità sono quelli esterni campionati dal Clock, che potrebbero non rispettare i tempi di Setup e di Hold, quindi i segnali *sincroni*.
Attenzione! Spesso enable e load sono sincroni, non vanno dimenticati.

*Nota*: tutti i segnali sincroni che sono legati a qualche altro segnale sincrono, possono essere considerati stabili per tutta la durata del primo segnale (ad esempio un segnale di LOAD e i vari Li)

Una correzione per la metastabilità possibile è legare gli ingressi a dei nuovi segnali dicendo:
$$L_i.D=L_{i}^{'}$$
Immaginando che $L_i$ sia il segnale che arriva dall'esterno mentre $L_{i}^{'}$ quello dopo un flip flop 


## VHDL

primo step: le *librerie*
![[Pasted image 20231216151257.png]]


secondo step: dichiara l'*entity*, il dispositivo
![[Pasted image 20231216151331.png]]

con PORT si listano tutti i segnali provenienti o andanti verso l'esterno.
Posso prevedere:
- segnali std logic IN
- segnali std logic OUT
- vettori std logic IN e OUT
- buffer std logic
- buffer vettori std logic

buffer sono segnali in uscita ma che possono essere anche letti. di solito si usano per gli stati interni del dispositivo, ad esempio nei contatori.

terzo step: costruisco l'*architecture* per l'entity
![[Pasted image 20231216151539.png]]ù

definisco variabili (segnali di appoggio) per eventuali filtri di metastabilità

quarto step: definisco i *process*
![[Pasted image 20231216151650.png]]

devo specificare i segnali che attivano il processo, di solito il clock ed il reset asincrono.
all'inizio del pezzo relativo al clock-segnali sincroni si caricano i segnali per cui si era preparato il filtro anti-metastabilità.. poi implemento la logica

fine: chiudo il pezzo dell'architettura e apposto
![[Pasted image 20231216151814.png]]

