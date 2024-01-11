Prendo in considerazione il [[Modello Statico]].
Il Fan-Out è un parametro statico indispensabile al corretto funzionamento del dispositivo.

**DEF**: esprime il numero massimo di carichi che possono essere connessi ad un dispositivo in contemporanea (paralleli all'uscita dello stesso).

$$\large N_{max} = min\{ \,\frac{I_{oh}}{I_{ih}},\frac{I_{ol}}{I_{il}}\,\}$$

*Commento*: Siccome sappiamo che i modelli elettronici funzionano per segnali elettrici, i segnali in uscita non solo devono trasportare informazione ma anche sufficiente "potenza" per far funzionare i dispositivi successivi.
Per questo il numero di dispositivi che un singolo può pilotare dipende dalla corrente da quest'ultimo erogabile! Perchè se eroga tantissima corrente allora può alimentare un esercito, altrimenti beh ecco abbiamo qualche limitazione. 

>Fan out risponde alla domanda "Qual è i tale che F trasporta correttamente la sua uscita a tutti gli A_i?"
![[Pasted image 20231101152949.png]]