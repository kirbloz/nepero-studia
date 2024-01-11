Sono i dispositivi digitali Medium Scale Integration, successori dei SSI (small Scale Integration).

Dove i SSI realizzano i gate, dunque le *porte logiche*, con basso fan in, oggi sono sfruttate per i buffer..
.. I MSI sono detti anche *registers*, contengono da 200 a 2000 transistor e funzionano tipicamente a 4 bit.
Possono essere
- [[Dispositivi Combinatori]] (convertitori, sommatori, comparatori, moltiplicatori..)
- [[Dispositivi Sequenziali]] (memorie, contatori, shift register..)

---
### Descrizione dispositivo elettronico
Ci sono diverse modalità con cui si può *descrivere* un dispositivo digitale
- *Livello Layer* (strati di fabbricazione)
- *Livello Transistor* (come sono connessi, S e D dei transistor o le celle CMOS)
- *Livello Gate* (descrizione della funzione, tabella di verità in termini di somme di prodotti)
- *Livello RTL*-Register Transfer Level (descrivo come collegamento di blocchetti funzionali) tipica

Gli MSI sono i mattoncini LEGO con cui si descrivono sistemi complessi. Questa descrizione si dice "RTL".
#### Somma di Prodotti (SOP)
Supportano la SoP. Vedi nello specifico [[Somma di Prodotti]]