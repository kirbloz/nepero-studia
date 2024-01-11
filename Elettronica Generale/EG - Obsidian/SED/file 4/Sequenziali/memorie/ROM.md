Read Only Memory, sono scritte/programmate già direttamente dal costruttore.
E' non volatile e *non* può essere cancellata

Si sfruttano per quel microcodice "comodo" o comodo da avere su HW dedicato.

La si può programmare seguendo uno di questi due paradigmi:
- *LOGICA FUSE* si prevede un percorso conduttivo che si interrompe a comando (1->0). 
  Si chiama programmazione mediante corrente.
>	Riempio la griglia di diodi e brucio con una $I\sim\infty$ tutti quelli che non mi servono

- *LOGICA ANTIFUSE* si prevede un percorso isolante che si interrompe programmando (0->1).
  Si chiama programmazione mediante tensione.
  >Esempio: dei condensatori disposti a griglia che sul "comando" ricevono una scarica di tensione e quindi si fora il dielettrico => si crea un percorso conduttivo
  
Tutti questi collegamenti (o la loro assenza) sono permanenti! Hardwirati nel componente di memoria.

### Mask Programmed ROM
Usando DIODI.
![[Pasted image 20231205232303.png]]

Usando NMOS.
![[Pasted image 20231205232509.png]]