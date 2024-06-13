Glossario:
- [[#Proposizione 1]]: duale di D coincide con P
- [[#TH Dualità debole]]
- [[#TH Dualità forte]]

---
## Proposizione 1
![[Pasted image 20240131215649.png]]

Questa dimostrazione è tutta canata ma come cazzo si fa: ok ce lho fatta
### Dimostrazione
Consideriamo un P di minimo, quindi D sarà di max.
![[Pasted image 20240131215716.png]]
Prima di procedere trasformo D in un problema di minimo.

I vincoli - durante il passaggio del problema da max a min - subiscono solo un cambio di segno/predicato.
Per comodità nei prossimi passaggi, prima traspongo anche tutti gli elementi:
$(\lambda^{t}\,A)^{t}\leq (c^{t})^{t}\quad \Rightarrow \quad A^{t}\,\lambda \leq c$  
E poi sistemo i segni. 

![[Pasted image 20240131215746.png]]

Ora calcolo il duale di D, che sarà un problema di massimo, in incognita $(\lambda)$, coefficienti $(-b)$ e termini noti $(-c)$. 
- per scrivere i vincoli inverto l'ordine di prodotto e traspongo le incognite
![[Pasted image 20240131215844.png]]
>$(-\lambda)=x$
>$(-A^{t\lambda)}= x^t(-A^t)$

E lo ritrasfromo in minimo:
![[Pasted image 20240131215856.png]]
Coincide con P.        $\square$


## TH della Dualità
[[TH Dualità Debole]]
[[TH Dualità Forte]]