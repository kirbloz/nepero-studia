Un elemento circuitale può assorbire o generare potenza, in base al verso della corrente rispetto alla polarità dell'elemento.

Una carica che attraversa un generico bipolo da $A$ a $B$ in $\Delta t$ subisce una variazione di energia pari a $$\Delta w = v \cdot \Delta q$$
Si definisce la potenza assorbita come derivata dell'energia sul tempo:
![[Pasted image 20240105095629.png]]
Si stabilisce che i versi sono *coordinati* (o associati) se la corrente entra dal $+$, e questi elementi sono detti utilizzatori perchè assorbono potenza.

La potenza è sempre definita in termini istantanei ma in realtà è una funzione del tempo. Per cui per calcolare l'energia si integra:
$$ w(t_1,t_2) = \int_{t_1}^{t_2} v(t)\cdot i(t)dt$$
- Se la potenza assorbita è costante uso $\Delta w = P_a \cdot \Delta t$

---
La potenza assorbita dai multipoli si calcola come l'unione di $n-1$ bipoli:
![[Pasted image 20240105100009.png]]

---
## Conservazione della potenza

*Enunciato*
La somma algebrica delle potenze assorbite da tutti gli elementi di un circuito è nulla in ogni istante.
$$\sum_k P_k(t)=0$$
- La conservazione della potenza non aggiunge nulla alle LK perchè è da loro che deriva. Può però essere utile per confermare i risultati con queste ottenuti.


DIMOSTRAZIONE:
![[Pasted image 20240105100414.png]]

## Teorema di Tellegen

In un generico circuito vale la conservazione della potenza $\sum v_k\,i_k = 0$, inoltre le LK forniscono informazioni solo relative alle interconnessioni nel circuito e non sulla topologia.
*Enunciato*
Consideriamo due circuiti A e B con *identica topologia*, li intendo come black box, non ho informazioni sui componenti o altro ma entrambi hanno due terminali esterni con cui si collegano e per questi sono definiti una tensione ed una corrente. 

Le tensioni e le correnti di A e B rispettano le stesse LKC ed LKT:
![[Pasted image 20240105100811.png]]

*Conclusione*
Tellegen è una proprietà topologica derivante dal concetto di circuito come interconnessione di scatole nere.

