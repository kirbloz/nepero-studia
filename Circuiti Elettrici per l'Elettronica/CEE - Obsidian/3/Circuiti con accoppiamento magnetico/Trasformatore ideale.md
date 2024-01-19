Modello molto semplificato, si trascurano tutte le perdite (ohmiche) e si considera nullo il flusso disperso (perdite magnetiche, isteresi).

Costruiamo così:
- 4 terminali
- 2 avvolgimenti su un nucleo ferromagnetico
 ![[Pasted image 20240106120158.png]]

Il flusso magnetico $\Phi$ è concatenato con tutte le spire di entrambi gli avvolgimenti, e dalla legge di Faraday si vede:
$$ \begin{array} \\v_1 = N_1 \frac{d\Phi}{dt} \quad \quad v_2 = N_2 \frac{d\Phi}{dt} \\ 
v_2=\frac{N_2}{N_1}v_1
\end{array}$$

I terminali sono accoppiati a due a due, per cui esistono due tensioni e due correnti indipendenti => doppio bipolo!
Dall'elettromagnetismo: $\overline B = \mu \overline H$
con $\overline H = 0$ all'interno del nucleo $\oint \overline H \cdot d \overline l = N_1i_1 + N_2i_2$
da cui $i_2 = - \frac{1}{n}i_1$ 

Così ho calcolato le due relazioni caratteristiche del doppio bipolo resistivo:
$$ \begin{array}  \\ 
v_2=\frac{N_2}{N_1}v_1 \\
i_2 = -\frac{N_2}{N_1}i_1
\end{array}$$

### Proprietà circuitale

1. la potenza assorbita in ogni istante è nulla
![[Pasted image 20240106121141.png]]
2. *trasformazione di resistenza*: se il secondario (induttore) è chiuso su un resistore $R_L$ allora la resistenza di ingresso che vede il primario varrà:
![[Pasted image 20240106121219.png]]

>La potenza erogata dal gen di tensione è la stessa che il resistore ciuccia e dissipa

### Limiti modello
- E' indipendente dalla frequenza, trasforma tensioni e correnti anche in continua. Ma in regime costante non c'è induzione magnetica
- Se lo si corto circuita si viola la LKT
- A vuoto invece, la corrente nel primario è nulla
 ![[Pasted image 20240106121335.png]]