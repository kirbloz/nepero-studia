Categoria di dispositivi che può realizzare funzioni logiche [[Somma di Prodotti|SoP]].
Sta per AND, OR, INVERTER. 
Le tabelle della verità ci danno un'espressione di una funzione F:
$$F = F \text({Tabella Verità}) = \text{SoP}$$
Ma la Sum cos'è? OR
Il Product? AND

$\Rightarrow$ è dunque possibile avere funzioni dove dalle varie righe della LUT si selezionano solo quelle con "1" in uscita (o se mi conviene - perchè sono di meno - gli "0" e in quel caso sarebbe !F)

**Qual è la cosa bella di questa organizzazione?**
Tutti gli ingressi vengono portati a delle AND, le cui uscite entrano a loro volta in un OR. E poi può avere il negatore programmabile.
Questo è il circuito base per realizzare tutte le SoP; quindi per descrivere tutte le funzioni F che possono essere espresse tramite LUT.
![[Pasted image 20231203181159.png]]

**NB**: il ritardo tra IN e OUT sarà costante, qualunque sia la funzione logica implementata il tempo di propagazione sarà il medesimo.
>Tphl e Tplh sono fissi

**Qual è la cosa brutta?**
Il limite è il fan-in.
Ciascuna uscita avrà #ingressi quindi delle porte AND ciccione! E' fisicamente insostenibile ad una certa.
Tipicamente si gestiscono bene fino a 6 ingressi, quindi 2^5 = 32 ingressi per la porta OR.
### XOR, il negatore programmabile
In realtà si comprende anche lo XOR:
![[Pasted image 20231203141042.png]]
E' la base della somma binaria.

Nel buffer c'è il problema del ritardo, dove Q arriva ad un tempo, ma !Q deve attraversare prima un NOT, e per cui i due segnali, per un certo periodo di tempo, non sono opposti.
![[Pasted image 20231203141306.png]]

**Come si ottiene un segnale negato sincrono?**
Porto il segnale a due porte XOR, così realizzate.
![[Pasted image 20231203141421.png]]
![[Pasted image 20231203141555.png]]
A XOR 0 = A
A XOR 1 = !A

Ottengo i due segnali nello stesso istante.