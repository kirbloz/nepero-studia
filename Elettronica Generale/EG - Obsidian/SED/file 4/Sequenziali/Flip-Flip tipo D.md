Li rappresentiamo così sti sburini:
 ![[Pasted image 20231204235807.png]]
E diremo: $$\text{Out(t) = F( In(t), In(t-T), Out(t-T) )}$$

![[Pasted image 20231205000337.png]]


Ste due immagini non so cosa siano:
> Gli impulsi generati da disallineamento temporale tra i percorsi NON devono influenzare il comportamento del componente (o di quelli ad esso collegati)
![[Pasted image 20231204235819.png]]
![[Pasted image 20231204235828.png]]

### Pro
Il valore !Q nel FF è ottimo e non ha ritardi, a differenza del Latch che per ottenerlo si caccia a cascata un NOT.
FF sfrutta gli XOR per avere sia output che !output disponibili nello stesso istante - allineati.

### Caratteristiche dinamiche
- I **dati** (o linee sync di set/res) devono essere *stabili* un certo tempo *prima* del fronte attivo del clock
  $\Rightarrow$ *tempo di set up* $T_s$ 
- I **dati** (o linee sync di set/res) devono essere *stabili* un certo tempo *dopo* del fronte attivo del clock
  $\Rightarrow$ *tempo di hold* $T_h$ 
- Si deve rispettare la massima frequenza $F_\text{max}$  e la minima larghezza di impulso di clock e set/res async.

![[Pasted image 20231205000621.png]]

Vedi [[Meta-stabilità]].
>In genere si cerca stabilità 20ns prima fino a 5ns dopo il segnale di clock.

*Nota Bene*: i Flip Flop ignorano l'ingresso se non si verifica un fronte di salita del clock. 
Per cui non esiste il ritardo input-output, bensì il *ritardo clock-output*.

---
### Circuiti con FF
Cos'è sta cosa un clock: è un contatore! Sono alla base dei sequenziatori.
![[Pasted image 20231205000027.png]]

## Differenze con Latch
![[Pasted image 20231205000125.png]]

