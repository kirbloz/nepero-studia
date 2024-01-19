
## Equivalenza
La sintesi di un bipolo con $Z$ impedenza data è un problema con più soluzioni.
![[Pasted image 20240108143940.png]]

Un generico bipolo *induttivo* è sempre equivalente a (a)$\quad X>0$
Un generico *capacitivo* invece, a (b)$\quad X<0$

>Duale con le ammettenze:
>![[Pasted image 20240108144045.png]]

---

### Implementazione più semplice di una impedenza
Sintetizzare una $Z=10+j5$ in regime a $\omega=1000\,\,rad/s$. Cosa significa?
$X=5>0$ bipolo induttivo
$R=10$ bipolo resistivo
![[Pasted image 20240108144732.png]]
Realizzazione in *serie*
$\Rightarrow$ La cosa più semplice è una resistenza $R=10$ in serie a un induttore con reattanza $X=5$. Come la trovo?
$X_{L}=\omega L = 5 = 10^{3}L \quad \Rightarrow\quad L = 5\,mH$

Realizzazione in *parallelo*
![[Pasted image 20240108144738.png]]
Cambia qualcosa? Calcolo l'impedenza per scoprirlo:
$Z= \frac{10\cdot 5j}{10+5j} = \frac{10j}{2+j} = \frac {10j\cdot(2-j)}{5}$
$Z = 2+j4$
che è un impedenza diversa! 
$X=4>0$ ancora induttivo
$R=2$ ancora resistivo, ma diversamente.

**Questi due bipoli sono equivalenti in regime sinusoidali, anche se hanno impedenze diverse**
**Comunque la realizzazione più semplice è quella in serie**



