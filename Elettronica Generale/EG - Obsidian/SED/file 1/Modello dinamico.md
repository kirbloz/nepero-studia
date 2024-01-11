## Dinamico ideale
![[Pasted image 20231110184431.png]]

*Ipotesi*: interruttori istantanei -> l'uscita segue istantaneamente l'ingresso
*Realtà*: esiste un **ritardo di propagazione**
Si modellizzano con dei capacitori

## Dinamico reale
![[Pasted image 20231110184656.png]]

$T_{pd}=T_{i}+T_{f}+T_{o}$
Ritardo totale è la somma del tempo di propagazione del segnale nello stadio di ingresso, nella funzione, e nello stadio d'uscita.

### Ritardi

#### Modellizzare i ritardi
$C_{in}$ influenza il ritardo in ingresso e $C_{out}$ quello in uscita. Semplifico modellizzando da 4 capacità separate a solo due.
![[Pasted image 20231110185622.png]]
$C_{pd}$ saranno le capacità interne della funzione, che consideriamo inglobare le $C_{out}$

*Pilota* vede $N$ *ricevitori*, dunque una $C_{tot}=N \cdot C_{in}$
Il $T_{o}$ tempo di propagazione dell'uscita (+funz) dipende da questa $C_{tot}$
>Un altro modo è usare i buffer per isolare gruppi di dispositivi ricevitori, per alleggerire la capacità vista dal pilota

#### Soluzione
Problema del fan out dinamico, da adattare con buffer. Ritardo inaccettabile. Sfrutto i [[Trigger Smidth]].

---
Molti dispositivi detti *buffer* hanno funzione logica ID (effetto logico nullo) e servono solo ad adattare le caratteristiche elettriche statiche/dinamiche o per ovviare a limitazioni funzionali (connessioni fisiche possibili).
>Noi modellizziamo In e Out=F(In) come vettori a dimensione uno, perchè concettualmente l'informazione è una, ma il segnale può realizzarsi fisicamente in modi diversi.

Vediamo [[Stadio di uscita dinamico]]


### Dissipazione di potenza dinamica
![[Pasted image 20231110190002.png]]
=> le capacità modellizzano i ritardi ma anche la dissipazione di potenza dinamica
>Perchè le $I_{p}$, durante la commutazione, caricano o scaricano $C_{tot}$ e $C_{pd}$

Energia immagazzinata nella commutazione $E=Q\cdot V_{p}/2$
Con $Q= (C_{pd}+C_{tot})\cdot V_{p}$ la potenza è pari a $P=2f\cdot E$

La potenza dinamica dissipata risulta $$P=(C_{pd}+C_{tot})\cdot f\cdot V_{p}^2$$
ove $2f$ è la frequenza delle commutazioni. 