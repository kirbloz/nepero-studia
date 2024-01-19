
>Cenni sulla trasformata di fourier:
>Ogni forma d'onda si può esprimere come la somma di sinusoidi a frequenze diverse. Fourier permette di scomporre una forma d'onda nelle sinusoidi armoniche che la compongono

La *risposta* di un circuito dinamico dipende dalla frequenza. 
La *risposta in frequenza* è la risposta del circuito alla generica sinusoide con pulsazione $\omega$
- In *regime lineare* la risposta in frequenza caratterizza completamente il comportamento del circuito con qualunque ingresso.

Vedi sotto

---
Tutto a livello teorico...


**DEF** :
 sia dato un circuito in regime sinusoidale alla pulsazione $\omega$.
 Chiamo *ingresso* un singolo generatore indipendente con fasore $V_{in}$
 Chiamo *uscita* una qualunque variabile circuitale di interesse (esempio $V_0$)

Il circuito simbolico è resistivo lineare e quindi so che esiste una relazione di proporzionalità tra la tensione in ingresso e la variabile circuitale.
$$V_{0}= F(\omega)\,\cdot V_{in}$$
![[Pasted image 20240109002714.png]]
**DEF** :
 la funzione $F(\omega)$ si dice *funzione di rete* e non dipende dal generatore ma dalla pulsazione che caratterizza il circuito. E' un numero complesso che dipende SOLO dalla pulsazione.
 In generale vale che 
 ![[Pasted image 20240109002706.png]]

---
tutta la classificazione ma mi rifiuto

---
### Proprietà

- Ogni funzione di rete è una *funzione razionale reale* (un rapporto di polinomi a coefficienti reali) nella variabile complessa $j\omega$

- Ogni funzione di rete si ottiene risolvendo un sistema di equazioni lineari con coefficienti $j\omega$ o $(j\omega)^{-1}$ derivanti dai componenti dinamici

- Le indico tipicamente con $F(j\omega)$ e hanno la forma
- ![[Pasted image 20240109002930.png]]


## Risposta in frequenza
>La *risposta* di un circuito dinamico dipende dalla frequenza. 
>La *risposta in frequenza* è la risposta del circuito alla generica sinusoide con pulsazione $\omega$

Per calcolarla si parte dalla generica funzione di rete $V_{0}=F(j\omega) V_{in}$
Che vedo come:
![[Pasted image 20240109003129.png]]
Antitrasformo la risposta come
![[Pasted image 20240109003143.png]]

---

Proviamo a fare un riassuntino...
La **funzione di rete** è $$\overline F(j\omega) = \frac{X_o}{X_{in}}$$
- l'ampiezza della funzione di rete è $|\,F(j\omega)\,|$
- la fase della funzione di rete è la differenza di fase tra il fasore in uscita e quello in entrata quindi $\phi(\omega) = \theta_{o}-\theta_{in}$

---

La **risposta in frequenza** è$$X_{o}=\overline F(j\omega)\cdot X_{in}$$
- l'ampiezza della risposta in frequenza si chiama *risposta in ampiezza* ed è il prodotto tra l'ampiezza della funzione di rete e l'ampiezza del fasore in ingresso $$
|\,X_{o}\,|=|\,F(j\omega)\,|\cdot|\,X_{in}\,|
$$
- la fase della risposta in frequenza si chiama *risposta in frequenza* ed è la somma della fase della funzione di rete e del fasore in ingresso $$\angle{X_{o}} = \phi(\omega)+\theta_{in}$$
---




L'espressione della **RISPOSTA IN FREQUENZA**  è univocamente determinata da due valori
- la *risposta in ampiezza*, il modulo della funzione di rete $|\,F(j\omega)\,|\,X_{m}$
- la *risposta in fase*, la fase della funzione di rete $\theta+\phi(\omega)$
- 
