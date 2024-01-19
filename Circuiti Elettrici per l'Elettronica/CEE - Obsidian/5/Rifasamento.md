![[Pasted image 20240108204445.png]]
- Il generatore modellizza la sorgente di energia
- Il carico è l'utilizzatore 
- La linea di trasmissione ha resistenza finita piccola $R_l$ e quindi la tensione sul carico non è quella nominale

*Problema*: la tensione di lavoro sul carico deve essere fissa! (in valore efficace)
- la differenza tra tensione reale e nominale diminuisce se la corrente di linea è più bassa
*Problema*: potenza dissipata dalla linea $P_{d}=2\,R_{l}\,I^{2}_{\text{l, eff}}$

*Obiettivo*: ridurre la corrente di linea in modo da ridurre le perdire e avvicinare $V$ a $V_s$
- la potenza attiva sul carico vale $P_{u}= V_{eff} \, I_{l,eff}\, \cos \phi$

*Soluzione*:
Dall'espressione di potenza attiva (parte reale di $S$) vedo che posso<span style="background:#affad1"> mantenere la potenza e tensione di carico</span> così
- aumento il fattore di potenza
- riduco la corrente di linea

**DEF** :
 si chiama *rifasamento* l'operazione che consente di ridurre lo sfasamento tra tensione e corrente sul carico
### Esempio
![[Pasted image 20240108205103.png]]

*Carico*: motore elettrico, carico induttivo con $R \ge 0$ e $X_L > 0$

*Problema*: variare lo sfasamento da $\phi_1$ a $\phi_2$ a parità di potenza attiva $P_{u}$
Dal grafico del vettore di potenza complessa si osserva che la differenza sta nel valore della potenza reattiva $Q_i$

*Idea*: posso ridurre la potenza reattiva inserendo un componente che contrasti $X_L>0$ ad esempio un **condensatore di rifasamento** in parallelo con reattanza $X_{C}<0$
$$Q_{2}= Q_{1}+Q_{C}< Q_{1}$$

IPOTESI:
tensione e potenza attiva sul carico sono pari al loro valore nominale
![[Pasted image 20240108205645.png]]


---

**RIFASAMENTO COMPLETO**
Questo sarebbe il caso più ottimale
![[Pasted image 20240108205807.png]]
Significa portare in completa fase i e v per la potenza attiva effettiva sul carico.
Tuttavia potrebbe volerci una capacità dal valore eccessivo, quindi ci accontentiamo di arrivare ad un fattore di potenza sopra una soglia minima (di solito 0.9)

>Il rifasamento è cruciale per le applicazioni reali: in contesti industriali servono elevate potenze sui carichi, quindi si lavora con altissime correnti di linea. Questi carichi sono di solito induttivi, ma il procedimento è analogo per quelli capacitivi


- funziona perchè linee poco dispersive
- aggiungere capacità ci fa risparmiare potenza dispersa