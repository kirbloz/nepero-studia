Problema: $V_s$ in arrivo è nella zona di incertezza. Come mi comporto? NON CAMBIARE!
Sono a comportamento prevedibile anche in zona di incertezza.
Si introduce la *memoria* dell'ultimo stato valido assunto dal componente.
>Si sfrutta il meccanismo fisico dell'isteresi

"Mantieni l'ultimo ingresso valido riconosciuto" -> sposta la soglia appena cambiato

Utile  quando si interfacciano disp lenti e veloci.
![[Pasted image 20231115141437.png]]
### Modello e stadio di ingresso
<span style="background:#affad1">Caso dispositivi con IN:Schmidt</span>
Ai livelli statici di tensione in ingresso (Vil e Vih) si sostituiscono i livelli di transizione $V_{tn}$ e $V_{tp}$ .
Le caratteristiche sono le seguenti:

- Non c'è più la [[Zona d'incertezza]] = l'uscita è nota per tutti i valori dell'ingresso tra 0 e alimentazione.

- *Cambia il significato di rumore!* Vedi [[Schmidt-Trigger#Rumore]]

- Durante la commutazione scambiano in ingresso correnti più elevate. Vedi [[Schmidt-Trigger#Lentezza & Fan-Out]]

- Sono più lenti, del 50%. Vedi [[Schmidt-Trigger#Lentezza & Fan-Out]]

- Si utilizzano per *squadrare* i segnali
	- adattano logiche lente verso quelle veloci
	- adattano il fan-out dinamico (quando Cl>>Clo)

#### Rumore
Prima l'isteresi pulisce dal rumore allontanando le soglie. Lo fa sfruttando V_tp e V_tn, migliora tantissimo l'immunità al rumore durante la commutazione, oltre che velocizzare i fronti lenti.
	$V_{in}\leq V_{tn}$ allora posso applicare $V_{h}$ rumore prima che l'informazione IN cambi.
	Se $V_{ol}=V_{in}$ allora $V_{h}=V_{tp}-V_{ol}$
	Se $V_{oh}=V_{in}$ allora $V_{h}=V_{oh}-V_{tn}$ 

**Threshold**
0: V_tn mantengo 0
0: V_tp vado a 1
1: V_tn vado a 0
1: V_tp mantengo 1

![[Pasted image 20231115135223.png]]
![[Pasted image 20231115141628.png]]

#### Lentezza & Fan-Out
Se ho un dispositivo ST allora $I_{ih}=I_{il}=$ ad esempio 10, trovo un fan out di 100. Molto bello!

Ma durante la commutazione?
Il pilota commuta tra 0 e 1 e la sua corrente OUT cambia direzione: ogni ricevetore vuole $I_{tp}$. Ma $I_{tp}$ è il max che il pilota eroga! Non può darne a tutti in contemporanea.

I più vicini commuteranno prima, la loro corrente in IN vedrà un picco, poi scende quando la commutazione è finita: solo a quel punto iniziano a commutare anche gli altri => in *ritardo*
Questo si chiama Fan-Out dinamico, di commutazione
![[Pasted image 20231115150524.png]]

#### Ritardo
Studiamo il ritardo che caratterizza i circuiti con dispositivi con ingresso ST.
![[Pasted image 20231115151244.png]]

pagina 19 file 2
I generatori di ritardo realizzati mediante questo circuito sono di bassa qualità (i livelli dipendono dalla temperatura e dalla tensione di alimentazione)

>Si può realizzare ritardo intenzionalmente mediante sequenze pari di porte NOT o contatori

### Ingresso astabile

pagina 18 file 2