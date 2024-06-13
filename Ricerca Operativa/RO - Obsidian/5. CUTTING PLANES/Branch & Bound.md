pagina 115 di pezzella c'è una sintesi dell'algoritmo
![[Pasted image 20240204170536.png]]
![[Pasted image 20240204170546.png]]

---

Glossario:
- [[#Idea]]
- [[#Funzionamento]], operazioni di branch, criteri di fathoming (e bounding)
- [[#Strategie di esplorazione]]

---

![[Pasted image 20240204160535.png]]
![[Pasted image 20240204160621.png]]

## Idea
Alla base funziona tutto sul fatto che:
1. si calcola l'ottimo del rilassamento continuo
2. se l'ottimo è intero ho finito. altrimenti genero due sotto problemi disgiuntoi introducendo due vincoli del tipo
$$x_{i}\leq \lfloor x_{i}^{\ast}\rfloor\quad \quad x_{i}\geq \lceil x_{i}^{\ast}\rceil$$
*NB* questi vincoli non eliminano soluzioni intere. le partizionano in due problemi figli.
il numero di sottoproblemi è comunque esponenziale, quindi comunque tempi esponenziali

## Funzionamento
![[Pasted image 20240204161043.png]]
Fin qui tutto ok nulla di nuovo.

<center>OPERAZIONI DI BRANCHING</center>
![[Pasted image 20240204161149.png]]
![[Pasted image 20240204161217.png]]

<center>CRITERI DI FATHOMING</center>
Quando è possibile voglio evitare di esplorare tutti i figli. 
Si adottano diversi criteri di decisione. Questi sono tutti gli scenari in cui posso fermare il branching:

1. *rilassamento continuo impossibile*: i tagli di branch sono incompatibili con i vincoli iniziali. chiudo il nodo.
2. *rilassamento continuo soluzione intera*: ho trovato l'ottimo del $PLI$. Ho finito.
3. *regola di bounding*: chiudo il nodo (termino la generazione di sottoproblemi) sfruttando informazioni che ho ottenuto da altre zone dell'albero
>$\Rightarrow$ ad esempio se in un altro ramo ho trovato una $z^{\ast}_{PL}$ INTERA migliore della soluz frazionaria appena trovata, mi posso fermare: troverei solo di peggio

<center>CRITERI DI BOUNDING</center>
Suppongo di aver trovato $x^{h}$ soluzione ammissibile intera tale che     $c^{\intercal}x^{h} \geq z_{PLI}^{\ast}$ 
Considero un nodo $k$ qualsiasi e so l'ottimo del rilassato è sempre $\leq$ dell'ottimo intero $$z^{k}=\min\{c^{\intercal}x: x\in P_{k}\}\quad\leq \quad \min\{c^{\intercal}x:x\in X_k\}$$

Per cui se dovessi trovare $z_{k}\geq c^{\intercal}x^{h} (\geq z^{\ast}_{PLI})$ 
E' inutile proseguire! $X_k$ non contiene ottimi migliori.

## Strategie di esplorazione
![[Pasted image 20240204163754.png]]
![[Pasted image 20240204164856.png]]
	depth first                                    breadth first
![[Pasted image 20240204164909.png]]![[Pasted image 20240204164936.png]]

![[Pasted image 20240204165018.png]]
![[Pasted image 20240204165115.png]]


