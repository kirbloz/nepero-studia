I Simple PLD sono il tipo più antico e rudimentale di PLD.
Sono realizzati come *una matrice di AND seguita da una matrice di OR*.

Sono dispositivi veloci, competitivi con le famiglie logiche TTL e CMOS. Non sono volatili, quindi memoria permanente.
Evolveranno nelle [[CPLD]], usate nelle periferiche programmabili ad alta velocità.

## Tecnologia
Utilizzano la i bipolari per realizzare le connessioni: in figura le X sono le possibili connessioni tra linee IN e porte AND, in quel punto andrà messo un BJT (o altro tipo di interruttore, ma le SPLD usano questi). 

DEF : 
 *matrice programmabile AND*,
 immagino di avere $J$ ingressi e alcune AND, anche solo 3.
 Avrò dunque il segnale $IN_i$ e $\overline {IN}_i$ per ciascuna AND.
 Ogni singola X è una connessione (metto/tolgo diodo - attivo/spengo BJT). 

>All'inizio della tecnologia si usavano memorie [[PROM]]: dunque logica FUSE e anti-FUSE[^1]: con la programmazione si prevede di far passare una grossa corrente per interrompere il collegamento (FUSE) oppure do una botta di tensione per forare un condensatore e creare un percorso conduttivo (là dove c'è isolamento, anti-FUSE)

Alla fine la programmazione è: seleziona una delle connessioni e imponi forte corrente/forte tensione

![[Pasted image 20231202102747.png]]

DEF : 
 *matrice programmabile OR*,
 Le porte OR vedranno tutti i *pterms* (uscite delle porte AND), e per selezionare le linee IN degli OR, c'è lo stesso sistema di connessioni della matrice AND.

>Alla fine la programmazione è: seleziona una delle connessioni e imponi forte corrente/forte tensione

![[Pasted image 20231202104627.png]]
## Caratteristiche generali
1. un AND plane per calcolare i *Product Terms*, o pterms
2. un OR plane per calcolare le somme, *Somme di Prodotti* o SoP
3. uno stadio di inversione perchè tutte queste funzioni nascono con *logica attiva bassa* - a causa dell'impiego di BJT, che ha "0" forte e "1" debole per cui si codifica l'informazione attiva nel livello "0", basso.

![[Pasted image 20231201150753.png]]
![[Pasted image 20231201151547.png]]
>Questa roba è solo uno schema logico! E' fisicamente inaccettabile il ritardo tra I0 e !I0 quindi vengono realizzati spiacciacandoci dentro degli XOR.

DEF :
 la *capacità*
 di questi dispositivi dipende dal numero di connessioni programmabili.
 
> CASO COMPLET. PROGRAMMABILE (PLA):
> Se ho $J$ ingressi, la mat AND avrà $2\cdot J$ ingressi, perchè voglio sia il segnale che il suo negato.
> Se ho $M$ uscite, avrò $M$ porte OR. 
> Immagino di avere $N$ porte AND: avrò nella <u>matrice AND</u> un totale di $2J\cdot N$ connessioni.
> La <u>matrice OR</u> avrà per ogni porta una connessione ad ogni porta AND quindi un totale di  $N\cdot M$.
> $\Rightarrow \quad N\,(2J+M)$ connessioni programmabili.

- Le porte AND e le porte OR sono economiche e occupano poco spazio silicio
- Le connessioni invece occupano tanto spazio silicio perchè devono essere ben isolati!
## Limiti
- Consumano molti fusibili. Anche se non li uso tutti nel programma, quelli stanno lì! Spreco.
- Scarsa flessibilità; in uno stesso dispositivo posso avere solo funzioni simili tra loro

SOLUZIONE:
Si mantiene l'architettura PAL ma personalizzando ogni singola uscita, grazie all'introduzione delle macrocelle $\Rightarrow$ dispositivi GAL.

![[Pasted image 20231201160328.png]]

## Classificazioni

### PLA
Famiglia di SPLD chiamata Programmable Logic Array.
Ha $N$ ingressi, $K$ uscite. Ogni uscita è il risultato di una *somma di prodotti*.

- Matrice di $M$ porte *AND* a $2N$ ingressi completamente programmabile;
>$2N$ perchè all'ingresso di ogni linea è posizionato uno XOR che permette di disporre sia di SGN che !SGN con lo stesso ritardo

- Matrice di $K$ porte *OR* a $M$ ingressi completamente programmabili;

Realizza $K$ funzioni logiche a $N$ ingressi indipendenti costituite da $M$ (max) minterms.
>$M$ indica la capacità della PLA
>Il numero di *fusibili* totali necessari per realizzare questa architettura diventa dunque: $M=2N\cdot M + M\cdot K$

Il numero di fusibili contenuti indica anche la dimensione del file binario necessario per programmare questo dispositivo.
![[Pasted image 20231201152700.png]]

### PLE
Sta per Programmable Logic Element.
La matrice degli AND è fissa mentre quella OR è completamente programmabile.
Ha $N$ ingressi, $K$ uscite. Ogni uscita è il risultato di una *somma di prodotti*.

- Matrice di $2^N$ porte *AND* a $2N$ ingressi fissa, chiamata SOP canonica.

- Matrice di $K$ porte *OR* a $2^N$ ingressi completamente programmabili;

L'architettura delle funzioni sfrutta le LUT, Look Up Table. Ossia sono [[Memorie|memorie]] configurate in lettura.
Realizza $K$ funzioni logiche indipendenti del tutto generali.
>Indirizzi=ingressi, dati=uscite

Il numero di *fusibili* è pari a $2^{N}\cdot K$.
Questa architettura risparmia numero di fusibili perchè la matrice AND non è programmabile sì, ma è *completamente sviluppata*.

Nell'immagine si hanno 4 ingressi per cui $2^4$ midterms e dunque $16$ ingressi alla per ogni SINGOLA porta OR.

![[Pasted image 20231201152821.png]]
### PAL
Realizzata con tecnologia bipolare PROM.

Sta per Programmable Logic Element.
La matrice degli AND è completamente programmabile mentre quella OR è fissa.
Ha $N$ ingressi, $K$ uscite. Ogni uscita è il risultato di una *somma di prodotti*.

- Matrice di $M$ porte *AND* a $2N$ ingressi completamente programmabile.

- Matrice di $K$ porte *OR* a $L$ ingressi fissa ($L<<M$);

Realizza $K$ funzioni logiche a $N$ indipendenti, costituite da $L$ (max) midterms.
>Indirizzi=ingressi, dati=uscite

![[Pasted image 20231201160314.png]]

---
## Riassunto evoluzione SPLD
>Si chiama Glue Logic ciò che queste schede realizzano (logichette specifiche che altrimenti necessiterebbero di un fottio di flip flop su schede generiche)

Si parte dalle PLA, che sono fully programmable, quindi hanno un fottio di fusibili.
Ne si vuole eliminare un po'! Esistono due ottimizzazioni:

1. "Elimino la Mat AND", la fisso, così ottengo le PLE; ovvero le normali memorie. 
   Avere la matrice AND fissa significa usare le porte AND per codificare tutte le possibili combinazioni di ingressi
   >2 ingressi: 4 porte AND cioè 00, 01, 10, 11.

Una PLE è l'equivalente di una memoria che utilizza come INGRESSI gli indirizzi, e come USCITE i dati memorizzati. 
Una Look Up Table! 
Ovviamente questa logica è vantaggiosa finchè il numero di ingressi è piccolo altrimenti il numero di fusibili totali esplode     ($2^{N}\cdot K$).

2. Questa roba non è molto efficiente dunque si è pensato di rendere fissa la matrice degli OR e tenere programmabile quella AND. Ottengo le PAL!
3.  Cosa rinuncio? Ogni pterm viene portato ad una sola porta OR.

I PAL si diffondono tantissimo dagli anni '80 e rivoluziona il modo di progettare sistemi elettronici abbandonando le logiche cablate: adotta i PAL per realizzare tutte le logiche di interfaccia, collante, quelle semplici!
Reggono bene anche ad un numero di ingressi modesto - non necessita di troppi fusibili.
Nascono i microcontrollori.


---
Note a piè di pagina:
[^1]:  Per capire questa cosa serve aver visto il funzionamento delle connessioni nelle memorie; 