Questi dispositivi li progetto con la Look Up Table.


## Decorders
Convertitori di codice da "compatto" a "espanso". 
Ad esempio voglio progettare un dispositivo che da 4 bit in ingresso ha 10 linee in uscita (da 0 a 9).
Calcolo che avrò $2^4$ possibili valori in ingresso e $16>10$ per cui esistono dei *gradi di libertà*: prevedo un'uscita che segnali la situazione di "ingresso non valido"
>Gradi di libertà: ingressi che non corrispondono a nessun uscita
- A questo esiste il segnale *ENABLE*, che è utile in questo caso mettendo l'uscita !E

### Demultiplexer
![[Pasted image 20231203143259.png]]
In questo dispositivo si sfruttano le linee $s_i$ per selezionare una delle uscite $O_j$ sulla quale viene convogliato l'ingresso $In$ se !E=0.
>Ovvero se è enabled, fa passare $In$ su una certa linea out.

L'*ingresso* può essere *implicito*: tutte le uscite NON selezionate vengono impostate OPPOSTE a IN.
>Ad esempio $In$=0 e le !S saranno 1. In pseudocodice:
![[Pasted image 20231203143616.png]]

Quando l'ingresso è $In$=1, allora il Demux è un decoder da $n$ a $2^n$


---

## Encoders
I MUX (multiplexer) possono essere considerati come convertitori di codice
Convertendo stavolta da "espanso" a "compatto", il MUX deve essere in grado di gestire conflitti (*priority encoders*, 74XX148); si dice che fanno gestione interrupt.
Immagino un multiplexer che converte da 2 bit (due selections) a un'uscita, scelta tra 4 ingressi possibili.

### Priority encoder
![[Pasted image 20231203142752.png]]
Questo dispositivo si occupa di *gestione interrupt*. "Non tutti gli interrupt sono importanti uguali!", ad esempio un NaN è peggio di un nuovo dato disponibile in arrivo da una periferica!

La tabella ha $N$ ingressi, descritti in $M$ righe da cui $K$ uscite.
- Ogni singolo ingresso può assumere lo stato "0", "1", "X" o essere una funzione a sua volta
- I pterm sono le uscite di porte AND con fan-in pari a $N$
- Il SoP-term che descrive ognuna $K_i$ uscita è l'output di una porta OR con fan-in pari a $M$
>Il fan-in delle OR è la principale criticità

In questo dispositivo inoltre:
$$!E_{out}= (!E_{in})$$
### Multiplexer
![[Pasted image 20231203173307.png]]

Mediante le linee $s_i$ si seleziona la linea $I_j$ che, qualora $!E=0$, va in $Y$.
>La selezione indica quale ingresso verrà riportato in uscita

- Se $!E=1$ allora l'uscita può essere in tri-state o negata o identificata da $!Y=Y$

NOTA: le uscite della LUT non sono in termini di 0 e 1 ma di AND con il minterm indicato dalla riga
Tipo $y= .. I0 \wedge E \wedge !s2 \wedge !s1 \wedge !s0 ..$

![[Pasted image 20231203173558.png]] 
---
