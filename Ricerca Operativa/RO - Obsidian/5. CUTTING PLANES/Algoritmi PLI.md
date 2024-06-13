Glossario:
- [[#Classificazione]]
- [[#Alg. Esatti]], che usano [[Piano di Taglio]] 
## Classificazione 
![[Pasted image 20240204124216.png]]

## Alg. Esatti
Questa categoria di algoritmi agisce così:
1. si calcola il rilassato passando da PLI->PL
2. SIMPLEX
3. trovato il vertice ottimo si studia se è intero o meno
   -  vertice intero $\Rightarrow$ ho trovato l'ottimo globale anche per PLI
   - vertice frazionario $\Rightarrow$ restringo l'area ammissibile e riprovo
![[Pasted image 20240204160111.png]]

---

<center>TECNICA DEI PIANI DI TAGLIO</center>
 ![[Pasted image 20240204124513.png]]
Qualora il primo vertice verificato dal simplesso non sia quello intero e quindi non ammissibile per $X$ devo "aggiustare" e "restringere" il rilassamento.
Poi si ricomincia con il simplesso.
Si possono sfruttare i [[Piano di Taglio|piani di taglio]]
>Idea:![[Pasted image 20240204125534.png]]
>In generale nella PLI si ambisce ad avere il [[Convex Hull]], perchè è la formulazione ottima. 
>I piani di taglio agiscono similmente alla restrizione delle coordinate su interi, ma restringono solo nelle prossimità della soluzione ottima.
>Quindi i piani di taglio non possono portare al convex hull a meno di casi particolari immagino.

---

<center>TECNICA BRANCH & BOUND</center>
Gomory è superato.
Vedi [[Branch & Bound]]
