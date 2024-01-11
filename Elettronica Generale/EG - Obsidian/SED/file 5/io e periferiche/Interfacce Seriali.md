*Interfacce Seriali*: un tipo di interfacce che si collegano a dispositivi periferici seriali come sensori o moduli BT, ma che possono anche realizzare -comunicazioni- tra due MCU.

---
### UART
Sta per Universal Asynchronous Receiver-Transmitter.
Si comporta come uno shift register con clock locale in *sovracampionamento*. 
COSA VUOL DIRE? boh

E' capace di *autodetect* del clock mediante la trasmissione di pattern speciali, o misurando la distanza tra start bit e stop bit.

Storicamente è un'interfaccia nata per l'RS232 ma oggi esiste ancora nei bus master-slave multipoint.
![[Pasted image 20231208213145.png]]

### SPI
Vedi [[SPI]].
