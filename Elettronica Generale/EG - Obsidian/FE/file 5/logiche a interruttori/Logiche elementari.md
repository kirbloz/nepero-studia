Logica binaria: l'elettronica lavora con logiche digitali, rappresentabili in codifica binaria, "0" e "1", spento e acceso. Dunque fa impiego degli [[Interruttore|interruttori]]. Vedi [[Livelli interruttori]].
L'interruttore da solo è buono per le correnti ma non per le tensioni. Bisogna *riferirlo ad una tensione*. Lo si può fare in quattro modi diversi.
### Logica attiva in uscita
Attiva alta e attiva bassa: sarebbe da riassumere ma non credo di aver capito. Sta nei livelli interruttori.
### Logica binaria
Questo deve essere tipo il primissimo approccio a questo tipo di logiche.. parto da una prima idea stupidissima e scarsissima.
![[Pasted image 20231031161732.png]]

*Circuito A:*
non c'è alimentazione; non c'è uscita.

*Circuito B:*
c'è un'alimentazione $+V$, $GND$;
c'è un'uscita in tensione;
- $R_a$ serve a evitare il CC tra massa e alimentazione;
- la codifica è "0" $\sim GND$, "1" $\sim +V$

*Circuito C:* //aggiunge roba a B
>c'è un'alimentazione+uscita in tensione; c'è una $R_a$ in uscita;
  codifica "0" $\sim GND$, "1" $\sim +V$;

<span style="background:#affad1">Si aggiunge</span> $R_b$, molto maggiore a $R_a$ per dare un segnale di "1" decente.
La necessità sorge dal fatto che quando si accende l'interrutore, <span style="background:#fff88f">scorre una corrente che fa cadere tensione su Ra</span>. Mettendo una resistenza in ingresso si *"forza"* la caduta maggiore (partitore di tensione) al nodo di uscita (dove Ra si attacca) => così permetto di avere un "1" molto più bello.

---

Così ovviamente però, le uscite saranno influenzate dalle correnti che attraversano il componente. Analizziamo il comportamento dal POV: circuito
![[Pasted image 20231031215122.png]]

-- IN = 0 --
Interruttore aperto. Il percorso tra $+V$ e $GND$ è interrotto.
Le correnti di carico però sono libere di entrare, e potrebbero esserci correnti minoritarie di base dal BJT. Dunque:
$V_{out} = GND + R_{a}\cdot i \quad \Rightarrow$    <span style="background:#d2cbff">"0" debole </span>

-- IN = 1 --
Interruttore chiuso. Scorre corrente tra $+V$ e $GND$ attraversando $R_{a}$ ed $R_{b}$.
Per le regole del partitore di corrente, il punto OUT è a metà tra due resistenze in serie e dunque il suo potenziale (tensione in uscita) dipenderà dal rapporto tra le due resistenze. In particolare:
$V_{out}=V_{in}\cdot {R_b}/({R_a+R_b})\quad \Rightarrow$    <span style="background:#d2cbff">"1" debole </span>

*Nota*: Il sogno sarebbe vedere un "1" bellissimo dunque $V_{out}= +V$ ma quindi la condizione sarebbe:
${R_{b}} / (R_{a}+R_{b}) \sim 1 \quad \Rightarrow R_{b} >> R_{a}$
Non sarà mai uguale a 1 questo rapporto! Ma mi ci posso avvicinare.

---

Cosa dice questa forza e debolezza del livello? Vedi [[Codifica Binaria]]
