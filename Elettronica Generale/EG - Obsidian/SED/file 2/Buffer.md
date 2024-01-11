Dispositivi con funzione logica identità (invertente o no) che servono per:
- risolvere problemi di fan-out statico => rigenera la corrente (garantisce $I_{ol}>I_{il}$ e $I_{oh}>I_{ih}$)
- risolve problemi di fan-out dinamico => rigenera la capacità ($C_{lo}>C_{in}$)

$\Rightarrow$ <span style="background:#fff88f"> Rigenerano il segnale e alleggeriscono il carico capacitivo</span> (lentezza)

![[Pasted image 20231112195147.png]] ![[Pasted image 20231115104639.png]]

---
Esistono dispositivi che integrano da 1 a 4 porte logiche. 
Queste porte possono avere un numero variabile di ingressi.
- Il fan-in è il numero di ingressi per porta logica => ci sono molte complicazioni se si vuole realizzare una porta NAND con 100 ingressi

---
Esistono buffer con ingressi o uscite speciali.
Ci sono quelli con uscita [[Open Collector]] o [[Tri-state]].
Ci sono quelli con ingresso [[Trigger Smidth]].
Ci sono quelli con uscite potenziate in corrente.

### Transceiver
Altro tipo di impiego del buffer, vedi [[Transceiver]]

### Schmidt Trigger
Vedi [[Schmidt-Trigger]]
