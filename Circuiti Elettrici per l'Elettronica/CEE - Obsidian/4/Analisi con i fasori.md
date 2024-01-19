Tutte le proprietà e tutte le tecniche di analisi dei circuiti resistivi sono utilizzabili anche per i circuiti simbolici e dunque per i circuiti dinamici in regime sinusoidale.

## LK
![[Pasted image 20240107113633.png]]
"La somma di sinusoidi isofrequenziali è una sinusoide il cui fasore è la somma dei singoli fasori"

## Metodo simbolico
Praticamente si associa al circuito vero e proprio (dominio tempo) uno trasformato simbolico (dominio fasori).

1. Sostituire ogni generatore indipendente con un generatore costante con fasore corrispondente
2. Sostituire ogni variabile con il fasore corrispondente
3. Sostituire ogni condensatore con un bipolo di impedenza $1/j\omega C$ e ogni induttore con uno di impedenza $j\omega L$
4. Analizza il circuito come fosse resistivo, ricavando i fasori desiderati
5. Ricava le grandezze sinusoidali con la legge di antitrasformazione
$$ \large \overline X = A\,\,e^{j\theta}\quad \Leftrightarrow \quad x(t) = A \,\, \cos (\omega t+\theta) $$

### Analisi nodale
![[Pasted image 20240107121640.png]]

Ho un circuito con $b$ bipoli (RLC e generatori di corrente sinusoidali), con $n$ nodi.
Si hanno dunque $n-1$ tensioni di nodo; il sistema è $(n-1)\cdot (n-1)$
Il sistema ha la forma $\quad Y_{n}V=I_s\quad$ e si scrive per ispezione.

$Y_n$ è la matrice simmetrica delle ammettenze di nodo
- $y_{ii}$ somma della ammettenze dei bipoli connessi al nodo $i$
- $y_{ij}$ opposto della somma delle ammettenze dei bipoli connessi tra i nodi $i$ e $j$
- $I_{si}$ somma algebrica dei fasori delle correnti dei generatori connessi al nodo $i$ 


SEMPLIFICATO:
![[Pasted image 20240107122242.png]]

### Analisi maglie
![[Pasted image 20240107122422.png]]

Ho un circuito con $b$ bipoli (RLC e generatori di corrente sinusoidali), con $n$ nodi.
Si hanno $m=b-n+1$ correnti di maglia; il sistema è $m\cdot m$
Il sistema ha la forma $\quad Z_{m}I=V_s\quad$ e si scrive per ispezione.

$Z_n$ è la matrice simmetrica delle impedenze di nodo
- $z_{ii}$ somma della impedenze dei bipoli nella maglia $i$
- $z_{ij}$ opposto della somma delle impedenze dei bipoli comunialle maglie $i$ e $j$
- $V_{si}$ somma algebrica dei fasori delle tensioni dei generatori connessi alla maglia $i$ (segno + se si entra dal -)

SEMPLIFICATO:
![[Pasted image 20240107122759.png]]


## Principio di sovrapposizione

I circuiti simbolici sono circuiti resistivi lineari; 
- in presenza di un *solo* generatore il fasore associato a ogni variabile circuitale è proporzionale al fasore del generatore.
- se ce ne sono di *più*, il fasore associato a qualunque variabile circuitale è pari alla somma dei fasori delle risposte ai singoli generatori


## Thevenin e Norton
Si applica uguale.
La tensione a vuoto è ora un fasore $V_T$ come pure la corrente di corto $I_N$.
La resistenza equivalente diventa l'impedenza equivalente $Z_T$.
Secondo le regole di trasformazione dei generatori si ha: $$ V_{T}= Z_{T}I_N$$

