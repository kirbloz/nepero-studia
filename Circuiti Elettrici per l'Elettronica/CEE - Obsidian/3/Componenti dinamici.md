In generale sono descritti da relazioni caratteristiche *differenziali*.
Il legame tra tensione e corrente non è più istantaneo e dipende dal momento nel tempo in cui si considerano le grandezze.


## Condensatore
![[Pasted image 20240105175632.png]]
![[Pasted image 20240105175711.png]]

>La dipendenza dal potenziale iniziale implica che il componente abbia memoria.
>Il modello reale è una coppia di conduttori (armature) separate da un dielettrico che intrappola le cariche.

**PROPRIETA'**
1. Quando la tensione è costante, il condensatore equivale ad un circuito aperto. Reagisce alle variazioni di tensione opponendosi a quelle brusche.
	La tensione ai suoi morsetti è *sempre una funzione continua*
	$v(t^+_0) = v(t^-_0)$
	
2. Immagazzina energia senza dissiparla. 
	Questa proprietà si deriva dal comportamento energetico, che risulta dipendere solo dal valore iniziale e finale. *Se la tensione è periodica, l'energia assorbita sul periodo è nulla.*
	Se la tensione iniziale è fissata, la max pow erogata si ha per v finale nulla. Si può quindi ricavare quanta energia si può immagazzinare.
	$$ w(t_0\, t_1) = -\frac{1}{2}Cv^2(t_0) \Rightarrow w(v)=\frac{1}{2}Cv^2 $$

3. Anche la potenza media assorbita sul periodo è nulla.
	Il condensatore è un *componente passivo*: in regime periodico l'energia assorbita su $T$ è $\ge 0$

---
## Induttore
![[Pasted image 20240105181156.png]]![[Pasted image 20240105181034.png]]
![[Pasted image 20240105181223.png]]
Duale rispetto al condensatore.

>La dipendenza dalla corrente iniziale implica che il componente abbia memoria.
>Il modello reale è un conduttore filiforme avvolto attorno a un nucleo di materiale magnetico => genera un flusso magnetico proporzionale alla corrente $\phi = Li$

**PROPRIETA'**
1. Quando la corrente è costante, l'induttore equivale ad un corto circuito. Reagisce alle variazioni di corrente opponendosi a quelle brusche.
	La corrente ai suoi morsetti è *sempre una funzione continua*
	$i(t^+_0) = i(t^-_0)$
	>Effetto scarica sui contatti degli interruttori.
	
2. E' un componente passivo non dissipativo
	L'energia immagazzinata dall'induttore dipende solo dalla corrente.
![[Pasted image 20240105181509.png]]


## Connessioni
Vedi [[Bipolo#Condensatori]] e [[Bipolo#Induttori]] per vedere come funzionano in serie e parallelo.
