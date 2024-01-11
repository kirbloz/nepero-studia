Il programma viene scritto in un file ASCII composto da due parti.
>Si sceglie il linguaggio ASCII perchè già usato per le PAL e così si possono fondere i due mercati.

I compilatori sono dei modelli abbastanza semplici. Se ho già descritto pin e funzioni, loro si occupano di generare un file *JEDEC* con la mappa dei fusibili (dove "1" sta per fusibile interrotto) e la documentazione.
$\Rightarrow$ dato un file JEDEC si può sempre ricostruire il file sorgente a meno dei nomi dei pin. La seq di 0 e 1 rappresenta la matrice degli AND e quella degli OR.
- Uno stesso source file può generare più file JEDEC

>I software si chiamano compilatori perchè devono decidere quali fusibili vanno usati: solo la mappa degli OR è fissa! 
>NB. se uso pochi collegamenti, tutti gli altri sono sprecati.
---

Il programma comprende dunque:

1. Si descrive l'interfacciamento del dispositivo a N piedini configurando ogni singolo pin. Si produce la *matrice interfaccia*.
>Si elencano CK INi nc gnd OUTi Vcc per tutti e 24 i piedini in ordine

2. Descrivo le funzioni come pin_i = f (pins_j) tramite una tabella di verità, con entries per ogni possibile ingresso.
   Si definiscono inoltre le abilitazioni dei FF, buffer 3-state.
![[Pasted image 20231202153848.png]]
![[Pasted image 20231202153912.png]]

### Pro e Contro
I vantaggi di questa architettura sono che hanno una temporizzazione fichissima e velocissima, in più sono facilmente programmabili

Ma hanno lo svantaggio che non posso cambiare la configurazione della mat OR perchè è fissa quindi se devo fare tante cose diverse, un dispositivo così non va bene!
Inoltre sono architetture sprecone di fusibili.
>Sono equiv a memorie da circa 5kbit
