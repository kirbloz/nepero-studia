Queste le sue equazioni descrittive.
![[Pasted image 20231203190632.png]]
![[Pasted image 20231203191122.png]]

*NOTA*: gli ingressi alle porte AND hanno tutti uno stadio con negatore programmabile in modo da avere ritardi di propagazione uniformi evitando la formazione di stati "spuri" di breve durata.

![[Pasted image 20231203190727.png]]

## Comportamento
![[Pasted image 20231203191146.png]]
![[Pasted image 20231203191155.png]]

Come realizzo Enable2 partendo da unìonda quandra? E lo attivo in corrispondenza del fronte di salita o del clock?
Lo voglio sul fornte di salita!

Situazione spiacevole: a causa del ritardo della porta NOT, il segnale di EN2 scatta mentre il segnale di ingresso A sta cambiando.
![[Pasted image 20231203191300.png]] ![[Pasted image 20231203191345.png]]

### Problemi del Latch
Nel caso di un comportamento sfortunato: enable scatta mentre il segnale IN commuta. Cosa memorizza il latch? Boh è imprevedibile.
*Però qualsiasi cosa sia, si stabilizza.*
Questa grande capacità deriva dal fatto che i sistemi digitali sono tutti rigenerativi e quindi il problema non è più l'impredicibilità, bensì la **meta stabilità**.

Vedi [[Meta-stabilità]].

- Ma quindi, se quando do alimentazione (accendo) ho un EN="0".. come si inizializzerà l'uscita?
	Per questo motivo è importante avere dei *circuiti di RESET*: vanno collocati a valle o a monte di tutto.

#### Reset Sincrono e Asincrono
Vedi [[Circuito di Reset]]

