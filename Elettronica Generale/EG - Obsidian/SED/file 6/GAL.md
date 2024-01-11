Generic Logic Array.
Una famiglia di dispositivi programmabili.
Il passaggio da PAL a GAL? Riprendo da [[SPLD#Limiti]].

## Tecnologia
- Il fan-in delle porte OR è variabile a differenza della PAL! 
	Si usa basso per le periferiche, e alto per i dispositivi centrali.
- Tutte le operazioni ora passano attraverso una MaC
#### Parametri temporali
La famiglia GAL ha 6 (pochi) parametri descrittivi fissi, ed indipendenti dal programma.

NB. per chi si dimentica Tpd o ritardo di propagazione è il ritardo tra fronte IN e fronte OUT di un'uscita combinatoria.
Ts e Th sono i tempi per cui il segnale DEVE essere stabile prima/dopo il fronte.
Il Tco è il ritardo tra fronte clock e fronte uscita registrata
Il Tco2 uguale ma usa come ingresso un segnale registrato[^1]. 
Il Tscs è il minimo periodo di clock
![[Pasted image 20231202144346.png]]
## Limiti
Il problema della  22v10 è che l'architettura è un po' rigida, i segnali devono uscire e rientrare in continuazione.. iniziarono ad essere 2, 3, 24.. schede 22v10. No buono.

Non va bene che tutte le MaC siano collegate ad un pin di uscita. Immagino di creare delle macrocelle collegate a tanti 22v10. Fico!
Vedi [[CPLD#Tecnologia]]

## Dispositivi
### GAL 22v10
Realizzati con tecnologia **CMOS EEPROM**.

*22* $\rightarrow$ numero massimo di ingressi. I pin fisici sono 24.
*10* $\rightarrow$ numero massimo di uscite.
*V* $\rightarrow$ dalla matrice AND programmabile escono un numero di *pterm* fissi verso la matrice OR; quella invece di mandare all'uscita direttamente, porta i dati elaborati ad una macrocella programmabile con 2 fusibili.
>2 fusibili per macrocella $\rightarrow$ 1 macrocella per uscita $\rightarrow$ 10 uscite $\rightarrow$ 20 fusibili

---
- Ideale per le macchine sincrone
- Fan-In delle porte OR (matrice OR) variabile
- Ha un modello temporale ideale


La GAL 22v10 è la prima scheda a far utilizzo delle [[Macrocelle]]. Riporto lo schema di una delle sue:
![[Pasted image 20231202100620.png]]
- Grazie ai 3-state in uscita è possibile programmare un PIN come IN o come OUT $\rightarrow$ flessibilità!
- I MUX eliminano il ritardo $\Rightarrow$ permettono di "uniformare il ritardo" per fare in modo che ogni uscita possibile sia disponibile nello stesso tempo delle altre;
- A causa del feedback di retroazione esiste un piccolo ritardo aggiunto;
 >quando questo riusciamo a minimizzarlo possiamo tirare il clock
 


### GAL 22RA10
Un altra scheda della famiglia GAL. Implementa una macrocella diversa, più versatile: è possibile impiegarla sia per macchine sincrone che per macchine asincrone.
E' comunque poco competitiva rispetto all'FPGA.
![[Pasted image 20231202102203.png]]

- Questa macrocella ha un buffer in uscita, abilitato da un segnale del PIN 13

---
Note a piè di pagina:
[^1]: Che cazzo è un segnale registrato