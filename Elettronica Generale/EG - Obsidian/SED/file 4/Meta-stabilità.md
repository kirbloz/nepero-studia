Dal [[Flip-Flip tipo D]] e [[Latch tipo D]]

DEF :
 la *meta-stabilità* è uno stato di un dispositivo che non permane nell'instabilità. Dopo un certo tempo (detto t di reazione) l'uscita DECADE su uno dei valori stabili previsti dalla progettazione.

- La meta stabilità decade grazie alla retroazione positiva nei dispositivi digitali. Lo stato in cui poi evolve è equiprobabile (50% a "0" e "1").
  Il tempo di risoluzione è al 99% il resolving time (50ns circa per i digitali).
  La probabilità che la meta stabilità sopravviva diminuisce esponenzialmente.
---

## Soluzione FF

1. Se l'ingresso "cambia subito dopo il clock" si verifica una *violazione di hold*
   	$\Rightarrow$ mantenere l'ingresso stabile un attimo dopo sgl di clock è sufficiente a evitare metà stabilità

2. Se l'ingresso "cambia esattamente con il clock" si verifica una *violazione di set up*
   	$\Rightarrow$ mantenere l'ingresso stabile un attimo prima sgl di clock è sufficiente a evitare metà stabilità

3. Garantire che un segnale qualsiasi abbia una *durata minima*, una larghezza "assicurata" permette dunque di avere stabilità.

Dunque facciamo delle osservazioni.
Anzitutto la *meta stabilità* è un problema diverso dalla zona di incertezza.
Si può verificare solo nei circuiti sequenziali (grazie alla retroazione che fa decadere il segnale ogni volta che si colloca in zona di incertezza).
Per questo è comunque vero che la zona di incertezza causa problemi non solo ai dispositivi combinatori ma a anche a quelli sequenziali, quindi tutti.
In sintesi:

Il nostro dispositivo si trova in meta stabilità quando si violano i valori minimi di almeno uno:
- $T_\text{hold}$ - segnale stabile dopo la commutazione
- $T_\text{set-up}$ - segnale stabile prima della commutazione
- $T_\text{w}$ - durata del segnale

DEF :
	tempo di *reazione* $\approx T_\text{set-up}+T_\text{hold}$
	la realizzazione di molte macchine sincrone richiede $T_\text{hold}<T_{\text{p,ck-o}}$
	

**Quanto sopravvive lo stato di "meta stabilità"?**
Si è già detto che il segnale "decade" su un valore.. questo suggerisce che la meta stabilità ha una durata stabilita da una legge esponenziale.

>Esempio: violazione del tempo di set-up. 
>L'ingresso commuta 2ns prima del fronte di salita del CLK.
>In output ci sarà meta stabilità. Il resolving time nei dispositivi digitali è circa 50ns.

- Entro 50ns dalla commutazione, la probabilità che un'uscita sia ancora in meta stabilità è $1/10^7$.
  Questo valore è paragonabile alla probabilità di malfunzionamento del componente: buona! Considero la meta stabilità come *evento improbabilistico*. Assumo che dopo 50ns il sengale sia decaduto a "0" o "1".
>Più il tempo passa e più diventa improbabile che lo stato meta stabile permanga.

#### Esempio
![[Pasted image 20231205152444.png]]
![[Pasted image 20231205152835.png]]
Quel pezzettino giallo è la <span style="background:#fff88f">finestra critica di campionameno</span>.
- Quel circuito rappresenta la concatenazione di due FF con medesimo CLK. La condizione per farlo è che il *ritardo programmabile CK+OUT del primo sia maggiore del tempo di Hold del secondo*. Altrimenti si violano le condizioni di stabilità.
- Questo vincolo di $$T_{h,\, (FF2)}<T_{plh,\,(CK-OUT)}$$
è terribile perchè non posso ridurre il tempo di propagazione se il tempo di hold è troppo grande! E' un limite all'ottimizzazione.

- FF2 non vedrà mai il segnale A commutare prima del segnale di CLK. Potrà al massimo vederlo "in ritardo" rispetto al CLK.
	- Il primo FF toglie la meta stabilià ma introduce il ritardo di *un colpo di clock*.
	  >Anticipare il ritardo? Posso provare a far lavorare FF1 sul fronte positivo e FF2 sul fronte negativo!
---	  
### Manipolare la finestra di ritardo
![[IMG_2023-12-07-10-51-53-213.jpg]]
Non mi piace che CLK e D commutino insieme. Potrei ritardare il D ma allora si vorrebbe un Tsetup ed un Thold circa pari, così da avere lo scarto di tempo.

In realtà si predilige avere Thold = 0 per cui si cerca un Tsetup molto piu elevato.

Dunque metto un condensatore in precedenza a CLK' per cui il D arriva prima del clock => ho il tempo di set up e non mi serve tenerlo troppo a lungo.
- Ho spostato e ottimizzato la finestra! 

---

## Circuiti robusti alla meta stabilità
mi sono segnato che alla prof interessa il circuito C a pagina 22
![[Pasted image 20231205162349.png]]

*A*: $V_{\text{out}}$ potrebbe essere metastabile per violazione di "set up" o di "hold".
	Il ritardo da $V_\text{in}$ a $V_\text{out}$ è variabile tra $T_{p}$ e $T_{p}+T_{ck}$ 

*B*: $V_{p}$ potrebbe essere metastabile per violazione di "set up" o di "hold". 
	Se $T_{ck}/2$ è superiore al *resolving time* allora $V_\text{out}$ si considera esente da meta stabilità.
	Il ritardo tra $V_{in}$ e $V_{out}$ è variabile tra $T_{p}+ \frac{1}{2}\,T_{ck}$ e $T_{p}+ \frac{3}{2}\,T_{ck}$

*C*: $V_p$ potrebbe essere metastabile per violazione di "set up" o di "hold". 
	Se $T_{ck}$ è superiore al *resolving time* allora $V_{out}$ si considera esente da meta stabilità.
	Il ritardo tra $V_{in}$ e $V_{out}$ è variabile tra $T_{p}+T_{ck}$ e $T_{p}+2\,T_{ck}$

**CASO C: analisi dei segnali**
![[Pasted image 20231205182124.png]]

- Il tempo di propagazione di FF1 - $T_{pd,\,FF1}$ fa si che FF2 campioni un segnale stabile, purchè $T_{pd,\,FF1} > T_{hold,\,FF2}$
- Il ritardo di propagazione complessivo ck-Vout varia tra $( \,T_{ck}+T_{pd,\,FF2})$ - valore in caso $V_{in}$ commuti un attimo prima di ck rispettando set up - e ($2T_{cl}+T_{pd,\,FF2}$) - valore in caso $V_{in}$ commuti poco dopo il clock rispettando hold.