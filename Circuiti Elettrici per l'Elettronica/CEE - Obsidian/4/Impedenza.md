Questo concetto si basa su "invece di trasformare le equazioni, si trasformano i circuiti"; si sfruttano le relazioni tra fasori associati alla tensione e alla corrente, che caratterizzano i vari componenti.

## Legge di Ohm simbolica
### Resistore
Nel dominio del tempo:
$$v(t)=R\,i(t)$$
Nel dominio dei fasori:
$$\overline V = R \overline I$$
- $|V| = R|I|$
- $\angle \overline V = \angle \overline I$
$\Rightarrow$ i due fasori sono allineati in termini di sinusoidi, quindi tensione e corrente sono in fase.
![[Pasted image 20240106184933.png]]

>La $\quad \overline V = R \overline I \quad$ è analoga alla legge di Ohm, è una relazione simbolica perchè i fasori *rappresentano*, ma non sono!, la tensione e la corrente nel resistore.

### Induttore

$$ \large v(t) = L\,\,d\,i(t)/dt \quad \Rightarrow \quad \overline V = j\omega L \, \overline I $$
Sfruttando la proprietà di derivazione.. Osservo che tensione e corrente sono in quadratura, con la corrente in ritardo sulla tensione.
![[Pasted image 20240106185243.png]]
### Condensatore
$$ \large i(t) = C\,\,d\,v(t)/dt \quad \Rightarrow \quad \overline I = j\omega C \, \overline V $$
Stesso procedimento.. La tensione e la corrente sono in quadratura, con la corrente stavolta in anticipo.
![[Pasted image 20240106185251.png]]

----
![[Pasted image 20240107120359.png]]

## Definizione

Dunque ogni singolo componente esprime una particolare relazione tra tensione e corrente.. può avere senso avere un concetto generalizzato ai bipoli..

>In regime sinusoidale anche l'induttore e il condensatore seguono una legge di Ohm simbolica che può essere riscritta in generale.

**DEF** :
 si chiama *impedenza* $Z$ il rapporto tra il fasore della tensione e della corrente imposto da un bipolo.
$$ \large Z = \frac{V}{I}\quad\quad V=ZI$$
![[Pasted image 20240106185523.png]]

>Come la resistenza ha la conduttanza, l'impedenza ha l'ammettenza $Y$.

*Nota Bene*: $Z$ è un numero complesso, è un rapporto tra due fasori.. ma non è un fasore.

---

Purtroppo la legge di Ohm simbolica (V=RI) non è valida per ogni singolo componente. Bisogna trovare altri modi per ricavare i fasori da associare a questi componenti.


- Per i componenti che hanno relazioni caratteristiche algebriche si fa una semplice *trasformazione* sfruttando le proprietà di omogeneità
![[Pasted image 20240106185855.png]]


- Per i componenti con relazioni caratteristiche differenziali si sfrutta anche la *derivazione* dei fasori. 
![[Pasted image 20240106185909.png]]

## Composizione
Si estendono al generico bipolo le regole viste per i resistori.

<span style="background:#fff88f">Resistenza -> impedenza</span>
- $N$ bipoli in *serie* sono equivalenti ad un bipolo con impedenza $\sum \limits_{k}Z_k$ 
<span style="background:#fff88f">Conduttanza -> ammettenza</span>
- $N$ bipoli in *parallelo* sono equivalenti ad un bipolo con ammettenza $\sum\limits_{k}Y_k$ 

![[Pasted image 20240107114715.png]]
![[Pasted image 20240107114742.png]]

### Stella - Triangolo
![[Pasted image 20240107115151.png]]![[Pasted image 20240107115208.png]]

### Millman
![[Pasted image 20240107120147.png]]

