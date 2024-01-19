**DEF** :
 riprendendo da [[Multipoli#Doppi bipoli resistivi]].
 i *doppi bipoli* sono quadripoli in cui due coppie di terminali rispettano la condizione di porta (corrente entrante uguale a quella uscente)
 - 2 tensioni e 2 correnti
 - 2 relazioni caratteristiche

**Intrinseci**: doppi bipoli per cui la condizione di porta è sempre verificata.
>Induttori accoppiati, trasformatore ideale, gen controllati. Sono *costruiti* apposta

**Estrinseci**: la condizione di porta è imposta dalla topologia, perchè ogni quadripolo chiuso su due bipoli si comporta come un doppio bipolo.
>Lo stesso quadripolo connesso in un altro modo può non essere un doppio bipolo. Imposto dalla topologia


Nota: sono importanti perchè di solito sono degli stadi di elaborazione del segnale. Alla porta uno si fornisce il segnale di ingresso, e alla porta due si preleva il segnale di uscita.

# Rappresentazione matriciale
Nel dominio dei fasori un bipolo dinamico con componenti lineari e generatori indipendeti ha la relazione caratteristica con questa forma $$\overline V=\overline Z(j\omega)\,\,I+V_T$$
![[Pasted image 20240110232603.png]]
- In assenza di generatori indipendeti, l'espressione si riduce al solo termine $\overline V=\overline Z(j\omega)\,\,I$

---
Ora definiamo le matrici
![[Pasted image 20240110232838.png]]
Applichiamo il [[Thevenin-Norton|TH di Thevenin]] al caso bi-porta
$$\large \left[V\right]=\left[Z\right]\left[I\right]+\left[V_T\right]$$
e senza generatori indipendenti..
$$\large \left[V\right]=\left[Z\right]\left[I\right]$$

>Per calcolare le matrici considero che ogni colonna di [Z] o [Y] è un circuito diverso, che impone grandezze nulle diverse

### Matrice delle impedenze
![[Pasted image 20240110232903.png]]
Si spezza il doppio bipolo in due circuiti per calcolare le grandezze descrittive.
Per mantenere le grandezze si impone un generatore di corrente. Per spezzarle invece circuito aperto.


1. Porta 1: generatotre di corrente
   Porta 2: circuito aperto $i_2=0$
![[Pasted image 20240110233034.png]]
- $Z_{11}$ impedenza di ingresso alla porta 1
- $Z_{12}$ impedenza di trasferimento dalla 1 alla 2

2. Porta 1: circuito aperto $i_1=0$
   Porta 2: generatotre di corrente
![[Pasted image 20240110233041.png]]
- $Z_{22}$ impedenza di ingresso alla porta 2
- $Z_{21}$ impedenza di trasferimento dalla 2 alla 1

### Matrice delle ammettenze
Stessa cosa, solo che le formule sono invertite quindi la $y_{21}$ è l'ammettenza di trasferimento dalla 1 alla 2.
Per mantenere le grandezze si impone un generatore di tensione. Per spezzarle invece corto circuito.

### Matrice ibrida
Fa schifo. 
Alla porta 1 mette il generatore di corrente (impedenza) e alla 2 il generatore di tensione (ammettenza).
![[Pasted image 20240110233954.png]]

Ha un duale che swappa i ruoli delle due porte.

### Matrice di trasmissione diretta
![[Pasted image 20240110234119.png]]
Non è possibile imporre corrente $i_{k}$ e tensione $v_{k}$ alla stessa porta in contemporanea.
Si combina imposizione di generatore di corrente/tensione (porta 1) - circuito aperto/chiuso (porta 2) 
=> bisogna calcolare 4 circuiti!

### Matrice di trasmissione inversa
Idem ma nell'imposizione swappa le due porte.

## Proprietà 
1. Gli elementi delle matrici sono TUTTE *funzioni di rete*. Vedi [[UNIVERSITA/CIRCUITI ED ELETTRONICA/FE/file 1/circuiti dinamici/Funzioni di Rete|Funzioni di Rete]].

2. E' possibile passare da una rappresentazione all'altra 
	 ![[Pasted image 20240110234415.png]]

3. Non sempre esistono tutte Z, Y, H, H', T, T'

## Modelli circuitali equivalenti
Sono realizzati tramite l'utilizzo di generatori controllati e impedenze/ammettenze opportunamente collocate.
- Z rapporto di trasferimento in corrente
- Y rapporto di trasferimento in tensione
- H rapporto di trasferimento in tensione/corrente
![[Pasted image 20240110234539.png]]

## Doppi bipoli con terminazioni
Si chiudono le porte con due bipoli.
Si usa una rappresentazione matriciale opportuna e si ricavano correnti e tensioni di porta.
![[Pasted image 20240110234716.png]]

Può aiutare nel calcolo della funzione di rete
![[Pasted image 20240110234745.png]]
Si determina il rapporto di trasferimento in tensione H.
$$H=\frac{V_2}{V_S}$$
Applicando la LKT alla maglia in ingresso (porta 1):
$$V_{S}= Z_{S}I_{1}+Z_{in}I_1$$
Si applica il partitore di tensione alla porta 2 basandosi sul circuito equivalente alla matrice ibrida.
![[Pasted image 20240110235146.png]]
$$V_{2}= Z_{21}I_{1}\cdot \frac{Z_L}{Z_L+z_{22}}$$
E si ricava $I_{1}$ dalla prima
![[Pasted image 20240110235139.png]]


# Connessioni

## Serie
![[Pasted image 20240112121306.png]]
Le porte 1 dei due doppi bipoli sono in serie così come le porte 2.
Si estende il concetto di serie:
- le tensioni si sommano
- le correnti sono uguali
![[Pasted image 20240112121220.png]]

Conviene sfruttare la rappresentazione Z se esiste.
![[Pasted image 20240112121240.png]]
## Parallelo
![[Pasted image 20240112121319.png]]
Le porte 1 dei due doppi bipoli sono in parallelo così come le porte 2.
Si estende il concetto di parallelo:
- le correnti si sommano
- le tensioni sono uguali
![[Pasted image 20240112121401.png]]

Conviene sfruttare la rappresentazione Y se esiste.
![[Pasted image 20240112121408.png]]
## Serie - parallelo
![[Pasted image 20240112121418.png]]
Le porte 1 dei doppi bipoli sono in serie, le porte 2 sono in parallelo.
E' un caso ibrido che non si estende dai bipoli.
![[Pasted image 20240112121456.png]]

Conviene sfruttare la rappresentazione H se esiste.
![[Pasted image 20240112121504.png]]

## Parallelo - parallelo
![[Pasted image 20240112121539.png]]
Le porte 1 dei doppi bipoli sono in parallelo, le porte 2 sono in serie.
E' un caso ibrido che non si estende dai bipoli.
![[Pasted image 20240112121545.png]]

Conviene sfruttare la rappresentazione H' se esiste.
![[Pasted image 20240112121551.png]]

## Cascata