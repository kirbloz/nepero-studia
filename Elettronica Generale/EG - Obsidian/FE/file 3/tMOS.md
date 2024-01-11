Sbrodolata su roba chimica che si deposita blblblbl
Deposito di dielettrico => è facile realizzare una capacità => effetto body

incolla immagine p11 
- $v_{G} \leq 0$ *ACCUMULAZIONE*
- $0 < v_{G}< v_{TH}$ *SVUOTAMENTO*
- $0 < v_{TH} < v_{G}$ *INVERSIONE*

### nMOS ad arricchimento
Riassuntino da slide 30 file 5.
![[Pasted image 20231101223703.png]]

INTERDIZIONE      
$V_{gs}< V_{t}$             $V_{ds}=0$                    
$I_{d} \rightarrow \,NA$   

OHMICA                
$V_{gs}> V_{t}$             $V_{ds}< V_{gs}-V_{t}$         
$I_{d}=k\, (V_{gs}-V_{t})\cdot V_{ds} \approx V_{ds}/R_{on}$ 

SATURAZIONE       
$V_{gs}> V_{t}$             $V_{ds}> V_{gs}-V_{t}$         
$I_{d} = \frac{k}{2}(V_{gs}-V_{t})^{2}\cdot \frac{1}{2}$

- Capacità in ingresso: $10 \text{pF}$, è lento a spegnersi (scaricare) ma veloce ad accendersi (caricare)
- Suscettibile a scariche elettrostatiche

![[Pasted image 20231101223654.png]]

---
**RIASSUNTO**
Il transistore nMOS ad arricchimento è un condensatore MOS con substrato p e aree laterali di drogaggio n (Source e Drain)
Il gate è isolato, per cui $I_{G}\approx 0$ e ho una capacità in ingresso

Esiste una tensione di soglia $V_{th} \sim 1$ che si confronta a $V_{gs}$ se $V_{ds}> 0$ 
- $V_{gs}-V_{th} << 0$ allora S e D sono isolate
- $V_{gs}-V_{th}<0$ si crea svuotamento -> corrente di perdita
- $V_{gs}-V_{th}>0$ allora iniza a crearsi un canale di conduzione che genera corrente.
	- Se $V_{ds}$ è PICCOLO, regione ohmica, lineare $\sim$ resistore
		$I_{ds}= k \cdot (V_{gs}-V_{th})\cdot V_{ds}$
	- Se $V_{ds}>V_{gs}-V_{th}$ (GRANDE), saturazione (pinch off)
		$I_{ds}= k/2 \cdot (V_{gs}-V_{th})^2$