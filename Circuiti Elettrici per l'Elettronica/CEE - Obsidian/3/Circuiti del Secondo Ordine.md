Circuiti con due elementi dinamici.
Sono descritti da un’equazione differenziale del secondo ordine.
Risoluzione meno semplice, la forma della risposta dipende dai parametri circuitali.
>Dinamica più ricca! Vediamo solo cenni sulle tipologie di risposta libera possibili.
- Circuiti RLC serie e RLC parallelo: sono perfettamente duali.

### RLC serie
![[Pasted image 20240106104344.png]]![[Pasted image 20240106104405.png]]
Si considera come grandezza incognita $v_C$
### RLC parallelo
Per dualità con la serie: ![[Pasted image 20240106104436.png]]
Si considera come grandezza incognita la $i_L$

## RLC
Alla fine sono descritti dallo stesso tipo di equazione.
$$\large \frac{d^2x}{dt}+2\alpha \frac{dx}{dt}+\omega_0^2x = 0$$

I parametri:
- $\alpha$ si dice *smorzamento*
- $\omega_0$ si dice *pulsazione di risonanza*

Le condizioni iniziali sono $x(0)$ e $dx(0)/dt$

Le soluzioni (più di una perchè è un'equazione omogenea) si presentano in forma esponenziale. Le soluzioni $s_1$ e $s_2$ sono:
$$\large s^2+2\alpha s+\omega_0^2=0$$
Le soluzioni sono anche dette *frequenze naturali* del sistema:
$$\large s_i = -\alpha \pm \sqrt {\alpha^2 -\omega_0^2}$$

---

### Risposta libera
In base ai valori dello smorzamento rispetto alla pulsazione di risonanza, si può classificare la risposta libera del circuito (e di conseguenza la forma delle soluzioni)

**SOVRASMORZATA**
$$ \large \alpha > \omega_0 $$
![[Pasted image 20240106110302.png]]
**SMORZAMENTO CRITICO**
$$ \large \alpha = \omega_0 $$
![[Pasted image 20240106110310.png]]
**SOTTOSMORZATA**
$$ \large \alpha < \omega_0 $$
![[Pasted image 20240106110315.png]]
**NON SMORZATA**
$$ \large \alpha = 0 $$![[Pasted image 20240106110326.png]]


## Luogo delle frequenze
Un altro modo per vedere la stessa cosa delle varie risposte libere di prima.
Al variare di $\alpha$ si osserva l'evoluzione delle frequenze naturali nel piano complesso. 

Nel caso di risposta non smorzata osservo che a causa di $\alpha=0$ le due soluzioni hanno un radicando NEGATIVO! Per cui finisco a lavorare con due numeri complessi e coniugati.

![[Pasted image 20240106113202.png]]

- $\alpha = 0$ le soluzioni sono immaginarie pure, coniugati. $x(t)$ assume la forma di un coseno
- $\alpha < \omega_0$ per sottosmorzamento, le soluzioni convergono sulla circonferenza di raggio $\omega_0$ (anche qui appare il coseno)
- $\alpha > \omega_0$ le soluzioni pistano via a 0 quasi subito, e divergono sull'asse reale (non ci sono coseno nè altro ma è tutto moltiplicato per l'esponenziale che schissa a 0)