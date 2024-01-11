Equazione derivabile dalla maglia:
$$\large v_{s}+ Ri + \frac{i}{j\omega C}=0$$
Se $v_{s}=v_{s}(\omega)$, cioè se dipende dalla frequenza:
$$ v_c(\omega)=v_{s}(\omega)\frac{1}{1+j\omega RC}$$


Il comportamento è diverso in base alla frequenza del segnale.

> **$\omega \approx 0$**
 Basse frequenze, tempi lunghi. $$\large v_c(t)=v_s(t)$$

>$\omega \rightarrow \infty$
>Alte frequenze, tempi brevi (di propagazione del segnale). $$ \large v_{c}= \frac{1}{RC}\int v_{s}(t)dt$$

**EFFETTO**: agisce come un filtro passa-basso: cioè "muta" le freuqenze alte, le taglia.


---
Dalle SLIDE DI CIRCUITI:
Si dice anche a forzante costante.
Il condensatore ha caratteristica inversa:
$$ v_{c}(t)= v(t_{0)}+ \frac{1}{C} \int_{t_{0}}^{t}i(x)dx$$

LKT: 
$$\begin{align*} v_{s} &= R i(t) + v_{c(t)} \\ v_{s} &= RC \frac{dv_C(t)}{dt}+v_{c(t)}\\ \frac{v_{s}}{\tau} &= \frac{dv_c(t)}{dt}+\frac{1}{\tau}v_{c(t)} \end{align*}$$

#### POV FISICO - RC
Di solito a $t_0$ si considera il *C* scarico:          $v_c(t_{0-}) = v_s(t_{0-}) = 0$     per cui anche       $i(t_{0-})=0$

Quando si applica    $v_s(t_{0+}) = v_s$     allora questa tensione cadrà prima sulla resistenza $R$ e poi sul condensatore: nella resistenza inizierà a scorrere una corrente che farà accumulare le cariche sulle armature del *C* - la cui tensione ai capi è descritta da $v_{c}(t)= v(t_{0)}+ \frac{1}{C} \int_{t_{0}}^{t}i(x)dx$ 

La tensione $v_{c}(t)$ aumenta, facendo diminuire $v_R$ ed $i(t)$ fino a $i(t) = 0$ perchè il condensatore è carico - pilotato dalla $v_s$ del generatore che lo ha caricato.

Il legame tra tensione iniziale ($v_{c,0}$)e finale ($v_{c}(t)$)è descritto da:
$$\large v_{c}(t) = v_{c,0} + (v_{s}-v_{c,0}) \,(1-e^{-\frac{t}{\tau}})$$
#### POV MATEMATICO - RC
Il circuito è descritto dall'equazione  $\frac{dv_{c}(t)}{dt} +\frac{1}{\tau}v_{c}(t) = \frac{v_{s}}{\tau}$ con soluzione
$$ \begin{align*} v_{c}(t) =& (v_{c}(0) - v_{s})^{\frac{-t}{\tau}}+v_{s} \\ x(t) =& (x(0) - x(\infty) )^{\frac{-t}{\tau}} +x(\infty)\end{align*}$$
