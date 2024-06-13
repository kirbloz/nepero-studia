Glossario:
- [[#Duale]]
- [[#Conversione]]
- [[#Criterio di ottimalità P e ammissibilità D]]
	- [[#Dim ottimo P coincide con ottimo D]]

---
## Duale

La teoria della dualità si sviluppa dal caso continuo della PL e afferma che per ogni problema di PL esiste sempre un suo problema duale e questo è unico.

Tra primale e duale esiste una forte associazione anche se P e D esistono su due insiemi diversi:
- P ha $n$ variabili, $m$ vincoli
- D ha $m$ variabili, $n$ vincoli
>Si noti che il binomiale per contare quante sol di base esistono danno lo stesso risultato.

![[Pasted image 20240131195333 1.png]]

Per due problemi P e D duali posso trovare soluzioni associate in coppie: alla *soluzione ottima di P e D* trovo il medesimo valore della FO, quindi se sono capace di risolvere uno dei due problemi, risolvo anche l'altro!

- Le soluzioni hanno lo stesso valore di FO ($z$ e $g$) ma i vertici trovati sono diversi!!
- L'unico valore di FO che identifica anche lo stesso vertice tra P e D è quello ottimo!

---

nota:
 ![[Pasted image 20240131200149.png]]

## Conversione
Si basa su "variabile P -> vincolo D" e "vincolo P -> variabile D"
Si scambiamo le dimensioni dei vettori monodimensionali, ma non cambia il numero di soluzioni (dopo aver fissato i gradi di libertà).

*PROBLEMA DI MINIMO*
![[Pasted image 20240131195544 1.png]]
- le variabili di D seguono il segno dei vincoli di P
- i vincoli di D assumono segno opposto rispetto le variabili di P

esempio:
 ![[Pasted image 20240131195646 1.png]]

## Criterio di ottimalità P e ammissibilità D
>Tutti i ragionamenti e dimostrazioni effettuati qua sotto sono un preludio ai teoremi della dualità [[TH Dualità Forte|forte]] e [[TH Dualità Debole|debole]].
>Per vedere questi concetti e proposizioni fissate con rigorosità, vedere quelli.

---

Ipotesi importante: considero di essere arrivato all'ottimo con un problema in forma standard. Il tableau avrà questo aspetto:
![[Pasted image 20240201105447.png]]

1. Per il primale l'ottimo vale quando
$$c^{\intercal}-(c^{\intercal}_BB^{-1}\,A)\geq 0$$
	Con la funzione obiettivo:
$$z:=c^{\intercal}x=c^{\intercal}_{B}(B^{-1}b)=(c^{\intercal}_{B}B^{-1})b$$
	L'incognita diventa il termine $(c^{\intercal}_{B}B^{-1})$ perchè $b$ sono i termini noti: questa $B$ è la *base ottima*.

2. Per il duale sappiamo che la funzione obiettivo ha questa forma: $$y:=\lambda^{\intercal}b$$
	Con incognita $(\lambda^\intercal)$ che quindi possiamo sostituire con il termine della base ottima del primale, perchè dalla definizione di problemi duali, *l'unico vertice ammissibile per entrambi, e per cui le basi coincidono, è l'ottimo*. Dunque la base che cerchiamo è proprio lo stesso vettore!
$$\lambda^{\intercal}b=(c^{\intercal}_{B}B^{-1})b$$
	Questo ci conferma che i due ottimi sono davvero lo stesso vertice ( e base ) con lo stesso valore.
	Sostituisco quindi quando trovato all'interno della condizione di ottimalità del primale:
	$$\begin{array} \\ \begin{cases}  \,\,c^{\intercal}_{B}B^{-1}\equiv \lambda^{\intercal} \\  \,\,c^{\intercal}-(c^{\intercal}_{B}B^{-1})A \geq 0 \end{cases} \\ \Rightarrow \\c^{\intercal} -\lambda^{\intercal}A \geq 0\\\lambda^{\intercal}A \leq c^{\intercal}\end{array}
	$$

*Osservazione*: dalle condizioni di ottimalità del primale si ottengono le condizioni di ammissibilità del primale, e viceversa (il viceversa lo dimostro sotto).
Si riconfermano tutte le ipotesi fatte.

Ma posso effettivamente dire che questo sia il vero ottimo del duale $D$?
![[Pasted image 20240201113810.png]]

### Dim: ottimo P coincide con ottimo D
Se $c^{\intercal}_{B}B^{-1}$ è l'ottimo di $P$, allora lo è anche per $D$? Sicuramente so che è ammissibile, quindi posso partire da quello.

Ipotesi di lavoro:
![[Pasted image 20240201114422.png]]
- Siamo all'ottimo di $P$. Allora l'ottimo si può scomporre così:
$$\begin{array}
 \\ c^{\intercal}x^{\ast}=c^{\intercal}_{B}\,x^{\ast}_{B}+(c^{\intercal}_{N}\, x^{\ast}_{N}\rightarrow 0)
 \\ c^{\intercal}x^{\ast} =c^{\intercal}_{B}(B^{-1}b)
\end{array}$$
E all'ottimo i vertici sono equivalente e le due funzioni obiettivo assumono lo stesso valore..
$$x^{\ast} \equiv \lambda^{\intercal\,\ast}\quad \rightarrow\quad c^{\intercal}x^{\ast} = \lambda^{\intercal\,\ast}b $$
Inserendo il valore dell'ottimo di $P$  e semplificando i termini noti:
$$\begin{array} \\ 
c^{\intercal}_{B}(B^{-1}b) = \lambda^{\intercal \, \ast} b \\ c^{\intercal}_{B}\,B^{-1} = \lambda^{\intercal\,\ast}
\end{array}$$
Ancora una volta ho trovato corrispondenza tra base ottima di $P$ e soluzione di $D$.
Però avevo in ipotesi l'ottimalità dei problemi.
Per cui la base ottima di $P$ è anche la soluzione ottima di $D$   $\square$

---

Da qui continua con [[Teoria della Dualità#TH Dualità debole]].


pics:
 ![[Pasted image 20240131200217.png]]
 ![[Pasted image 20240131200244.png]]


