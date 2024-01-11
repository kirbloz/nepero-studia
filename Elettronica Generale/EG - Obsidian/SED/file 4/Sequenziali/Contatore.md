Noi considereremo i contatori sincroni a 4 bit, con fronte attivo di salita.

Le loro caratteristiche:
- Organizzazione = binaria (BCD) ($\star$)
- Capacità = numero di bit
- Reset = sync o async
- Preset (LOAD) = sync o async
- UP/DOWN = carry/borrow

Segnali che questi cosi conoscono:
- !MR = master reset sync
- CEP = count enable input
- CET = count enable carry input
- CP = clock al fronte di salita
- !PE = parallel enable input
- TC = terminal count output (1111)

Un esempio con frequenza massima a 25MHz e tempo di propagazione clock-out di 28ns:
![[Pasted image 20231205234231.png]]

($\star$): una cosa essenziale per realizzare un contatore sincrono è che *tutte le uscite commutino assieme*. 
>Anche perchè è proprio la debolezza del contatore asincrono, se non commutano assieme si generano stati spuri fastidiosi.

Si può avere una funzione logica per preparare il dato input al contatore e averlo disponibile pronto.
Si attende un segnale di clock perchè gli FF leggano questo input: così ricevono tutti assieme - ed emettono anche tutti assieme.
![[Pasted image 20231205234541.png]]

- Al momento della salita del clock, tutti i $FF_{i}$ leggono i vari $Q_{i}\text{(t)}$ e li portano pronti all'uscita in $Q_i\text{(t+T)}$.
  Lì il nuovo numero incrementato attenderà di essere prelevato al prossimo fronte di clock attivo 
  >Questa tecnica si chiama sistema di campionamento (???)
  
![[Pasted image 20231205234914.png]]

La funzione logica è lo XOR, la somma binaria. Lega lo stato corrente con quello successivo.
![[Pasted image 20231205234928.png]]