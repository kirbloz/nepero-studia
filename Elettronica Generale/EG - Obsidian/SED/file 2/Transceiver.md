I [[Buffer]] transceiver adattano il FANOUT statico/dinamico per l'utilizzo di *bus bidirezionali*.

*Caratteristiche*: sono composti da due 3-state in antiparallelo.
Si organizzano in gruppi da 8 (comandi in comune) = 8 bit.
*Nota*: i transcriber reali non hanno quattro ingressi (A, B, X, Y) $\Rightarrow$ l'utente vede le linee !Sel e Dir (non X e Y).
>Per evitare guasti.

### Evoluzione
![[Pasted image 20231115111422.png]]
Aggiungo due AND ai 3-state in antiparallelo: questo mi permette di non avere mai A=1 e B=1 in contemporanea $\Rightarrow$ permette di gestire segnali bidirezionali.
>Evito i guasti!
### Tabella di verità
![[Pasted image 20231115111312.png]]
![[Pasted image 20231112195155.png]]

Qualunque valore assuma $Dir$, $A$ e $B$ sono isolati se $Sel=FALSE$.

---



