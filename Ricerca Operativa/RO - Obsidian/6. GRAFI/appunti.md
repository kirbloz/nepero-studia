


**ciclo hamiltoniano**
applico tree algorithm, euristico, trova un ciclo hamiltoniano grazie al concetto di minimo albero coprente. 
principali passi:
- calcola minimo albero coprente T
- crea un multigrafo euleriano raddoppiando i lati presenti in T
- costruisce il ciclo H prendendo i nodi senza ripetizione nello stesso ordine in cui compaiono nel grafo precedente

