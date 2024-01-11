Con gli interruttori si realizzano le [[Funzioni logiche]].

**DEF**: una *famiglia logica* è un insieme di dispositivi SSI (porte logiche) e MSI (contatori) che permettono di realizzare la maggior parte delle funzioni logiche e che sono accumunati da criteri progettuali e uno stesso processo tecnologico per la realizzazione.
- Hanno gli stessi livelli di tensione e di corrente (<span style="background:#b1ffff">codifica</span>)
- Hanno le stesse caratteristiche di assorbimento (<span style="background:#b1ffff">consumo</span>)
- Hanno gli stessi tempi di salita e discesa (<span style="background:#b1ffff">ritardi</span>)

### Diodi
E' possibile realizzare una famiglia logica utilizzando solo diodi?
~~Sì, però è una pessima scelta, i diodi sono interruttori senza comando, sono inefficienti.~~
No, perchè la logica a diodi non ha dispositivi (=tante porte elementari)
No, perchè non rispettano la condizione di immunità al rumore ($\star$)
Vedi in  [[Interruttore#Diodo]].
Esempi:
![[Pasted image 20231101172605.png]]![[Pasted image 20231101172616.png]]

*Commento*: di per sè la porta logica realizzata con i diodi funziona! Però ha un interfacciamento pessimo: nel senso che non rigenera i segnali. Nel senso che ha una barriera di potenziale in ingresso.
Questa barriera va gradualmente ad alterare il segnale, che non venendo rigenerato, dopo un tot di porte attraversate risulta completamente un'altra cosa!

![[Pasted image 20231101173100.png]]

Lo vedo chiaramente qui: suppongo di avere tre porte AND con ingressi (1,0) collegate tra loro. La funzione logica risultante è $A\cdot B \cdot C \cdot D$

A causa degli ingressi che diamo l'uscita sarà logicamente 0, ma elettricamente?
In ogni porta scorre corrente inversa, a causa della contropolarizzazione dei diodi, per cui risulta che per gli ingressi bassi ci sia $V_{in}=0$ ma in uscita quello che si legge non è zero, bensì la barriera di potenziale $V_{out}= 0.7V$

($\star$) Questa barriera esiste per ogni porta e si somma, portando una codifica di "0" a 2.1V => uno zero bruttissimo! <span style="background:#b1ffff">Per i diodi il rumore non è inteso come nei BJT, bensì come la loro stessa caduta di tensione.</span>

>Se il mio circuito avesse un'alimentazione su 3V, verrebbe interpretato come un "1", soprattutto se la codifica in ingresso mangia "un po' più" di quella in uscita. Terribile! 
![[Pasted image 20231101173727.png]]
### Bipolari
Se invece dei diodi, utilizzassi la tecnologia del BJT?
Vedi [[RTL]].

### Bipolari & Diodi 
-> cosa migliora?
Integro diodo
[[DTL]]

### Multiemettitore
-> cosa migliora?
multiemettitore
[[TTL]]

---

e la tecnologia nMOS?
[[CMOS]]

vantaggi soluzioni etc

---

famiglie e dispositivi reali p51

---
### Dai TE

RTL:
- Ha uno <span style="background:#affad1">"0" forte</span> ed un "1" debole su cui scambia molta corrente
  =>per leggere "1" serve $I_{ih}$ elevato, ma $I_{oh}$ non è sufficiente per pilotare abbastanza dispositivi
- Si accende con lo 0.7V (dalla V_be) per cui tutti i livelli logici sono schiacciati a zero

DTL:
- <span style="background:#affad1">Modifica lo stadio IN statico </span>per rendere i carichi più leggeri dove il pilota è debole (cioè sull' "1")
- Il diodo D1 alza la soglia in ingresso per ridistribuire i livelli logici che con RTL sono schiacciati
- Introduce concetto di *carico attivo*: ovvero resistenze e transistori in grado di assumere un valore di carico resistivo diverso in base allo stato logico. 
  Nel caso della porta NAND è l'insieme R2-R1-T2
      "0" IN, T2 è spento quindi la corrente scorre dall'ingresso a R1+R2
      "1" IN, T2 è accesp quindi la corrente fluisce la R1 in T2 ed il carico visto da D1 è solo R1

TTL:
- Ha un output tra 0 e 3.6V perchè T4-D1 hanno una barriera di 1.4V
- <span style="background:#affad1">Velocizzano la commutazione da "0" a "1"</span>
- T4 è veloce a spegnersi perchè lavora in polarizzazione attiva => erogare corrente per pilotare "1" non è un problema
- D1 deve evitare che la corrente di saturazione da T2-T3 accenda T4
- Consuma molto quando OUT "0" perchè T2 acceso e T4 spento => passa una corrente di saturazione nella resistenza R3 di scarico

