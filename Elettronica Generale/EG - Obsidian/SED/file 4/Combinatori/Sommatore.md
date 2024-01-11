![[Pasted image 20231203180707.png]]

Gli ingressi $n$ si contano sommando:
- $m$ bits per OGNI addendo
- CarryIN
Quindi $n=2m+1$
### Ripple Carry
"Si appoggia a stati di calcolo parziale per velocizzare il riporto del carry" => è possibile connettere in ripple-carry più moduli di questo tipo
![[Pasted image 20231203183809.png]]
In quel caso il ritardo del sommatore dipende anche da quanti bit uso perchè ogni singolo bit introduce il ritardo di propagazione dell'uscita di carry verso il suo successivo.

### Carry Look Ahead
![[Pasted image 20231203184007.png]] 
Questo è il classico full adder che disponiamo in schema a cascata:
![[Pasted image 20231203184040.png]]

E' possibile comunque *anticipare il calcolo del carry* per un gruppo di bit, diminuendo il ritardo complessivo.
Se dispongo di un fan-in elevato posso arrivare a trattare gli ingressi dei SoP terms come gruppi di bit.

## Dimensionamento AOI
Come ogni dispositivo AOI prevede una LUT a $n$ ingressi e $2^n$ righe - a meno di righe indifferenti - con $k$ uscite.
- fan-in AND: $n$
- fan-in OR: metà del numero delle righe se ci sono meno "1"; 
  altrimenti realizzo $!F$ e vado a fan-in $2^{n-1}$ 

## Dimensionamento LUT
Le LUT possono essere considerate come memorie usate in lettura ove si suppone di collegare gli ingressi agli indirizzi e le uscite ai dati.
- Per cui la memoria deve disporre di $n$ linee di indirizzi, $2^n$ celle.
- Le uscite determinano la capacità di ogni singola cella.
>8 bit => memoria organizzata a byte


