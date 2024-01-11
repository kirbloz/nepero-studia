Può essere di due tipi:
- Combinatoria
- Sequenziale

## Combinatoria
Vedi [[Dispositivi Combinatori]].
Può essere descritta come tabella dove:
$$\text{Out(t) = F(In(t))}$$

Ogni singolo ingresso ha la medesima interfaccia elettrica, tranne quelli Schmidt trigger dove $\text{In(t)=S(In(t),In(t-T))}$
![[Pasted image 20231203190118.png]]

## Sequenziale
Vedi [[Dispositivi Sequenziali]].
Può essere descritta come tabella dove:
$$\text{Out(t) = F( In(t), In(t-T), Out(t-T) )}$$
O anche:
$$\text{Out(t+T) = F( In(t), In(t-T), Out(t) )}$$
