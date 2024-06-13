Un modello matematico rappresenta un problema, con dei vincoli ed un insieme da cui pescare le varibili.
![[Pasted image 20230222170714.png]]

- x è il *vettore delle variabili* decisionali
>Le variabili decisionali sono "quello che cerco con il problema", i risultati attesi, i comportamenti che mi interessano
- f(x) è la *funzione obiettivo*
- g<sub>i</sub>(x) e h<sub>j</sub>(x) sono i *vincoli* del problema
>Un vincolo di uguaglianza rappresenta una retta (in R<sup>2</sup>).
>Un vincolo di disuguaglianza rappresenta sia una retta che il semipiano sup o inf ad essa. La retta in questo caso è la frontiera dell'insieme delle soluzioni.

## Classificazione problemi
Programmazione = ottimizzazione

La più generale possibile è la *programmazione non lineare* o [[NPL]]. 
- Suo sottoinsieme (f convessa e alcuni vincoli concavi) è la *programmazione convessa*. 
- Suo altro sottoinsieme è la *programmazione lineare* o [[PL]] dove sia la funzione che il dominio, che i vincoli sono convessi (o lineari).
>Un vincolo lineare è una somma algebrica con coefficienti scalari.
>Se esistono due o più variabili che si moltiplicano tra loro allora perdo la linearità.

- Un altro sottoinsieme è la *programmazione lineare intera* o *intera mista* [[PLI]], ove le variabili decisionali assumono valore intero.