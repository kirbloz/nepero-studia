
*Enunciato*
Siano $P= \{x \geq 0 : Ax \geq b\}$ e $D= \{\lambda \geq 0 : \lambda^{\intercal}A \leq c^\intercal\}$ non vuoti.
Per ogni coppia di punti $\tilde x\in P$ e $\tilde \lambda \in D$ vale
$$\tilde \lambda^{\intercal}\,b\leq c^{\intercal}\,\tilde x$$


 


*Dimostrazione*
Consideriamo i criteri di ammissibilità

- Primale:    $A\tilde x \geq b\quad \quad \tilde x\geq 0$
- Duale:      $\tilde\lambda \geq 0\quad \quad \tilde \lambda^{\intercal}A \leq c^{\intercal}$

Scriviamo una disequazione a partire da $A$
$$\begin{array}
\\ A \\
b\leq A\tilde x \\
\tilde \lambda ^ {\intercal}b \leq A \tilde x\leq c^{\intercal}\tilde x \\
\Rightarrow \\
\tilde \lambda^{\intercal}b\leq c^{\intercal} \tilde x
\end{array}$$
$\square$

---

*Osservazioni*:
1. " Le funzioni obiettivo di P e D si limitano a vicenda "
2. Se uno dei due problemi ha ottimo finito, allora questo porrà un upper bound (se P) o un lower bound (se D) per il suo duale.

---
pic
 ![[Pasted image 20240131200327.png]]
