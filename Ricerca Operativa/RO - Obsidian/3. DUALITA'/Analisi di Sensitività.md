Ipotesi: siamo all'ottimo.
Perchè ci interessa calcolare l'intervallo di variazione di $b$ o $c$? perchè realisticamente nel tempo, parametri e vincoli cambiano! quindi questo tipo di studio può essere ottima prevenzione/valutazione.

---
Glossario:
- [[#Definizione]]
- [[#Applicazione]]
	- nel caso dei [[#Termini Noti]] e [[#Coefficienti di costo ridotto]]
- Per proseguire [[Simplesso duale]]

---

Recappino:
- I prezzi ombra sono la soluzione ottima del duale, e misurano il contributo dato alla funzione obiettivo per ogni variazione unitaria $\Delta b$ dei termini noti

## Definizione

**DEF** :
 L'analisi della stabilità della soluzione ottima è lo *studio delle variazioni di un elemento per volta dei coefficienti $c_j$ o $b_i$* in modo che i vincoli saturi che determinano la soluzione ottima rimangano gli stessi[^1].

>" stabilità " sta per robustezza della soluzione rispetto alle perturbazioni nei dati. più è ampio l'intervallo delle variazioni ammesse, più la soluzione è robusta
---

Algebricamente si fa la derivata parziale della funzione obiettivo rispetto ad un certo coefficiente o termine noto:
![[Pasted image 20240201173607.png]]

E grazie al fatto che il problema è lineare, otteniamo che per il problea:
![[Pasted image 20240202160335.png]]

>Con $\Delta b$ e $\Delta c$ gli intervalli per cui la soluzione ottima rimane stabile.[^2]
>In questo scenario la soluzione ottima è nota e l'incognita su cui si lavora è $\Delta b$ o $\Delta c$
## Applicazione 

*ANALIZZIAMO LE VARIAZIONI DEI PARAMETRI $b$ TALI CHE MANTENGANO INALTERATA LA SOLUZIONE DI BASE OTTIMALE*

Ipotesi: problema di PL già risolto.
Definisco le condizioni necessarie e sufficienti perchè la base $B$ rimanga quella ottima:
![[Pasted image 20240202163704.png]]

Per il teorema sulle condizioni di ottimalità di un problema duale:

<center>" x* è soluzione di base ottima se esiste lambda * tale che* "</center>

1. $x_{B}^{\ast} = B^{-1}b \geq 0$                                                 amm. primale
2. $r^{\intercal}:= c^{\intercal}-c^{\intercal}_{B}B^{-1}A \geq 0$                                    amm. duale
3. $\lambda^{\intercal\, \ast} = c^{\intercal}_{B}B^{-1}$                                                    ortogonalità


Quindi si riconduce l'analisi di sensitività allo studio delle variazioni dei dati iniziali per cui (1) e (2) rimangono verificate

### Termini Noti
Sia P un problema di minimo dove $b$ è il vettore dei termini noti e $\Delta b$ è la sua variazione - l'incognita che cerchiamo.
Il problema è all'ottimo quindi $x^\ast$ è noto. Scriviamo in ipotesi le condizioni di ottimalità:

1. $x^{\ast} \geq 0 \quad \rightarrow \quad B^{-1}\,(b+\Delta b) \geq 0$
2. $c^{\intercal}-c^{\intercal}_{B}B^{-1}\,A \geq 0$                                  invariata

Osservo che l'unica condizione che cambia è la (1). Sarà quindi cio che uso per cercare l'incognita.
*Quando si varia un termine noto, la base rimane ottima SE E SOLO SE*
![[Pasted image 20240202164847.png]]

---

*Nota*
 Dalle condizioni di ottimalità di P e D osserviamo che le variazioni di $b$ influenzano

 - le coordinate di $x^{\ast}_B$ ( quali var in base e quali no )
 >immediato: $x_{B}^{\ast}= B^{-1}\,(b+\Delta b)$
 
 - il valore ottimo $f(x^{\ast})=z$ 
 >immediato: $f(x^{\ast}) = c^{\intercal}x^{\ast} \rightarrow c^{\intercal}_{B}B^{-1}\,(b+\Delta b)= \lambda^{\intercal\,\ast}(b+\Delta b)$

---

Le informazioni che servono per questo calcolo sono:
![[Pasted image 20240202170337.png]]
E cerco $\Delta b$ imponendo:
$$B^{-1}\Delta b \geq - B^{-1}b$$

---
### Coefficienti di costo ridotto
Sia P un problema di minimo dove $c_{N}^{\intercal}$ è il vettore dei CCR delle variabili fuori base, e $\Delta c_{N}^{\intercal}$ è la sua variazione - l'incognita che cerchiamo.
>Ci interessa solo $\Delta c_{N}^{\intercal}$ perchè $c_{B}^{\intercal}=0$ sempre.

Definisco per il problema cosa sono i CCR:
- $\overline r^{\intercal}$ := CCR pre variazione
- $\tilde r ^{\intercal}$ := CCR post variazione

Il problema è all'ottimo quindi $x^\ast$ è noto. Scriviamo in ipotesi le condizioni di ottimalità rispetto ai CCR:

1. $x^{\ast} \geq 0$                                 invariata
2. $\tilde r^{\intercal}=[c^{\intercal}-c^{\intercal}_{B}B^{-1}\,A] \geq 0$
     $=[\,0^{\intercal}\,;\, (c^{\intercal}_{N}+\Delta c^{\intercal}_N)-c^{\intercal}_{B}B^{-1}\,N] \geq 0$

Osservo che l'unica condizione che cambia è la (2). Sarà quindi cio che uso per cercare l'incognita.
*Quando si varia un CCR fuori base, la base rimane ottima SE E SOLO SE*
![[Pasted image 20240202171624.png]]


*NOTA BENE*
- $\overline r_{j}\geq 0$ è il MASSIMO DECREMENTO del costo $c_{j}$ per cui la base B rimane ottima.
>Sottraendo a $\overline r^{\intercal}$ una quantità maggiore di $\overline r^{\intercal}$ otterrei $\tilde r^{\intercal} < 0$ che indica che $B$ non è più la base ottima.
>L'unica eccezione perchè questo accada comunque ma vada tutto bene è quando si ha una soluzione degenere.






---

<center>FOOTER</center>
[^1]: I "vincoli saturi" sono quelli con slack = 0, detti anche vincoli attivi. Saturi perchè la soluzione sta sulla loro frontiera e quindi si usa tutta la risorsa che vincolano. Ovviamente quali slack sono = 0 indicano anche la base dell'ottimo, per cui volere che questi vincoli non cambino significa volere che la base ottima (cioè la soluzione ottima) non cambi. 
[^2]: Questa roba viene dal libro di Pezzella sui Problemi di Gestione della Produzione.