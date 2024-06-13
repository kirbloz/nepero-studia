O in italiano, teorema degli scarti complementari.

Glossario:
- [[#Intro]]
- [[#Teorema]] e [[#Dimostrazione]]
- [[#Significato]] che porta a [[Interpretazione Prezzi Ombra]]

---

Recappino:
- ogni problema P primale è associato al suo duale
- i vertici di P e D sono associati a due a due per valore della FO
- il numero di vertici di P e D coincide
- solo il vertice ottimo è medesimo per entrambi

Note:
- un vincolo soddisfatto con uguaglianza $\Rightarrow$ variabile di slack = 0
- un vincolo rimane in disuguaglianza $\Rightarrow$ la differenza = valore della variabile di slack

## Intro

**CONDIZIONE DI ORTOGONALITA'**
 Condizione molto potente che dal punto di vista pratico consentono di ricavare la soluzione ottima di D data quella di P e viceversa,
> Sono la base per lo sviluppo dei metodi primali/duali

Ipotesi: siamo all'ottimo.
1. variabile primale $x_{j}>0 \quad \Rightarrow \quad y_{m+j}=0$ vincolo duale
	   vincolo duale  $y_{m+j}>0 \quad \Rightarrow \quad x_{j} =0$ variabile primale

2. vincolo primale $x_{n+i}>0 \quad \Rightarrow \quad y_{i}=0$ variabile duale
	   variabile duale  $y_{i}>0 \quad \Rightarrow \quad x_{n+i} =0$ vincolo primale

Per esteso:
 ![[Pasted image 20240201192432.png]]
 >essendo una somamtoria di prodotti con termini tutti positivi, servono termini nulli peffozza. non ce stanno di negativi
 
 ---
## Teorema

*Enunciato*:
  $x^\ast$ e $\lambda^\ast$ sono soluzioni ottimali del primale e del duale se e solo:
  ![[Pasted image 20240201174858.png]]

>Le cond. di compl. slackness non sono solo una roba cool e comoda, sono proprio delle condizioni intrinsiche esistenti perchè l'ottimo esista (e sia equivalente tra P e D).

---
### Dimostrazione 

Si parte esplicitando le condizioni di ottimalità di due problemi P e D in forma canonica.
Ipotesi:
![[Pasted image 20240201185331.png]]

Dati $x^\ast$ e $\lambda^\ast$, questi sono ottimi per P e D se e solo se valgono i seguenti tre punti:
1. $Ax^{\ast}\geq b\quad \quad x^{\ast}\geq 0$                      ammissibilità di P
2. $\lambda^{\intercal\,\ast}\leq c^{\intercal}\quad \quad \lambda^{\ast}\geq 0$                     ammissibilità di D
3. $c^{\intercal}x^{\ast}= \lambda^{\intercal\,\ast} b$                                 FO coincidenti

>La (3) è verificata per ogni coppia di vertici P e D associati.
>L'unica soluzione che soddisfa anche (1) e (2) è il vertice ottimo.

- *Ammissibilità*
Combinando (1) e (2) si ottiene il [[TH Dualità Debole]]:
![[Pasted image 20240201190415.png]]

- *Ottimalità*
Mentre imponendo la condizione di ottimalità possiamo sostituire i predicati $\leq$ in $=$[^1]
![[Pasted image 20240201190520.png]]
Si osservi che lavoriamo con problemi di PL in forma standard che trasformano i vincoli in questa maniera:
$$Ax\geq b \quad \rightarrow \quad A(x+x_{s)}= b$$
Le variabili di slack risultano dunque essere la differenza " $Ax-b$ " !!
>Stesso ragionamento per il duale.

Le variabili del problema duale sono ortogonali alle slack del primale.
Le variabili del problema primale sono ortogonali alle slack del duale.
![[Pasted image 20240201191430.png]]![[Pasted image 20240201191436.png]]


![[Pasted image 20240131201159.png]]

## Significato
Vedi [[Interpretazione Prezzi Ombra]].
SIUM.

" Se mi trovo in una soluzione (ottima) di uno dei due problemi dove $\exists$ una variabile di slack con valore positivo ($x_{s}\neq 0$) allora questo significa che la corrispettiva variabile duale $\lambda_i$ sarà nulla, per garantire l'annullamento del prodotto "
![[Pasted image 20240201192403.png]]

---

## Footnotes

[^1]: Note su questo passaggio algebrico di riscrittura delle equazioni e raccoglimento:
![[Pasted image 20240201191600.png]]
