Realizzate mediante interruttori, sfruttano le [[Logiche elementari]].

*Nota*: tutti i dispositivi digitali sono **BUFFERED**, ovvero adattano correnti e tensioni per i dispositivi precedenti e successivi, qualunque sia la funziona logica che implementano.
>Grazie alla presenza degli stadi IN e OUT!

## NOT
Questa è la semplice porta NOT a interruttori simmetrici.
Con un "1" e uno "0" indeboliti.
E' la BASE. La partenza. La madre. MIA MADRE.

![[Pasted image 20231101164003.png]]

### NAND
La più fondamentale. 
Con le porte NAND si realizzano tutte le logiche, acnhe più complesse.

*Nota*:  $V_{ol}$ e $I_{oh}$ sono differenti da quelli della porta NOT => l'interfaccia OUT è diversa.

![[Pasted image 20231101164215.png]]

### NOR
Porta NOR. 

*Nota*:  $V_{oh}$ e $I_{ol}$ sono differenti da quelli della porta NOT => l'interfaccia OUT è diversa.

![[Pasted image 20231101164227.png]]



---
## Funzioni da interruttori
pagina 71
realizzare con cmos

*AND* = serie di interruttori
*OR* = parallelo di interruttori
*NOT* = porta elementare

pMOS -> conduce con "0" sul gate
nMOS -> conduce con "1" sul gate

![[Pasted image 20231102103749.png]]
![[Pasted image 20231102103804.png]]

### FCMOS
Data una funzione F, la realizzazione FCMOS consta di 
- un pull-up realizzato a PMOS che implementa F
- un pull-down realizzato a NMOS che implementa NOT(F)

*MULTIPLEXER*  slide 46

*ELEMENTO SWITCH* slide 47