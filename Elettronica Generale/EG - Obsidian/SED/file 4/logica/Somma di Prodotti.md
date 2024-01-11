Una modalità per descrivere i dispositivi MSI è tramite una tabella di verità per la funzione che realizza - quindi sfruttando le somme di prodotti.

![[Pasted image 20231203135143.png]]

### Temporizzazione
La rappresentazione circuitale ha ritardi variabili tra ingressi e uscita (ad esempio in un percorso deve attraversare una porta NOT in più).

La realizzazione a LUT ha ritardo fisso, pari al tempo di lettura della memoria *per ogni funzione logica*, indipendentemente.
- $N$ ingressi $\rightarrow$ memoria a $2^N$ bit
  Questo limita il fan-in!

![[Pasted image 20231203141026.png]]

---

### LUT
L'uscita di una tabella della verità può assumere vari stadi:
- "0"
- "1"
- "Z"
- "X"
- "not init"
- ...
Oppure può essere una funzione degli ingressi (SoP).