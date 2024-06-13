
- preso un problema di PL con vincoli di >=, le slack saranno $-x_s$ ma così ho matrice identità negativa nel tableau, e moltiplicando per -1 sminchio i termini noti. come mi comporto?
- come si leggono B, N, c_b etcetc dati un tableau iniziale e quello ottimo?

---

# Simplex
- vedi post it gialli attaccati sul muro
# Due Fasi
prima metto tutto ok (termini noti pos, aggiunta di var di slack) e poi aggiungo y 
![[Pasted image 20240205105657.png]]

porto in forma canonica
![[Pasted image 20240205105704.png]]

calcolo l'ottimo e 
- SOL. DEGENERE: rimane una y_i, ci caccio dentro una var og a caso (con CCR non nullo)
- VINCOLO RIDONDANTE: rimane una y_i ma nessuna var con CCR !=0 => significa che il vincolo di y_i era ridondante, per cui cancello la riga e basta

![[Pasted image 20240205105805.png]]

riscrivo la FO com'era
![[Pasted image 20240205105810.png]]

---

# Dualità

1. prima di iniziare, osserva il problema: $x=[0]$ è una soluzione ammissibile?
   se ad occhio c'è un vincolo di maggiore uguale con tutti + allora probabilmente non è ammissibile... ho due strade
   - metodo delle due fasi
   - passaggio al duale (se ho pochi vincoli, conviene! graficam)

![[Pasted image 20240202115739.png]]


2. controlla che soluzione con certi $\lambda_{i}=0$ sia/non sia ammissibile per il duale
-

## Simplesso duale
![[Pasted image 20240202173739.png]]



---

## Analisi di sensitività

<span style="background:#40a9ff">Per i TERMINI NOTI:</span>
- prendo $x^{\ast}$ per sapere quali variabili sono in base e quali no
- in base a $x^{\ast}$ prelevo le colonne dal tableau iniziale per costruire $B$
- $B^{-1}$ non lo calcolo, bensì leggo dal tableau ottimale le colonne delle variabili di slack
- scrivo il sistema $$[\,B^{-1}\,] [\,\Delta b_{i}\,]\geq -[\,B^{-1}\,][\,b\,] $$
E risolvo per il $\Delta b_i$ di interesse.


<span style="background:#fff88f">Per i COEFFICIENTI:</span>
- prendo $x^{\ast}$ per sapere come comporre $c^{\intercal}_N$ e $c^\intercal_B$ 
- partendo da $\overline r^{\intercal}:= c^{\intercal}-c^{\intercal}_{B}B^{-1}A \geq 0$ sempre verificato perchè $\overline r ^\intercal$ è il vettore CCR all'ottimo; definiamo il vettore CCR dopo la variazione $\tilde r ^\intercal$:

<center>FUORI BASE</center>
$$\begin{array} \\
\tilde r^{\intercal}:=\overline r^{\intercal}+\Delta c^{\intercal}_{N}\geq 0 \\
\Rightarrow \quad \Delta c_N^{\intercal} \geq -\overline r ^{\intercal}
\end{array}$$
1. si scrive il vettore incognite $\Delta c_N^\intercal$ 
2. si preleva $\overline r ^\intercal$ dal tableau ottimo 
3. si risolve il sistema per la variazione richiesta

<center>IN BASE</center>
$$\begin{array} \\
\tilde r^{\intercal}:=c^{\intercal}_N-(c^{\intercal}_{B}+\Delta c_{B}^\intercal)B^{-1}N \geq 0 \\
\tilde r^{\intercal}= \overline r^{\intercal}-\Delta c_{B}^{\intercal}B^{-1}N \geq 0\\
\Rightarrow \quad \Delta c_B^{\intercal}B^{-1}N \leq \overline r ^{\intercal}
\end{array}$$

1. si scrive il vettore incognite $\Delta c_B^\intercal$ 
2. si compone $B^{-1}$ come le colonne di slack dal tableau ottimo 
3. si compone $N$ ora come le colonne delle $x_N$ da $x^{\ast}$ ma prese dal tableau iniziale
4. si preleva $\overline r ^\intercal$ dal tableau ottimo 
5. si risolve il sistema per la variazione richiesta

---



# Modellizzazione 

- $x_1$ e $x_2$ non negative. si vuole $u=\min \{x_1\,,\,x_2\}$ 
si possono usare i vincoli disgiuntivi:
pongo FO: $\max u$ che spinge ad assumere il valore massimo nell'intervallo, che sarà poi il minimo dato dalla definizione:
$$\begin{array} \\
u \leq x_{1}\\ 
u \leq x_{2}\\
\end{array}$$
![[Pasted image 20240203154153.png]]

per adattarci al PLI, in termini di vincoli disgiuntivi cerchiamo un vincolo sempre attivo e uno verificato: invece di avere due variabili differenti, uso $y$ e $(1-y)$ 
$$\begin{array} \\
u - x_{1}\geq -M_1y_1\\ 
u - x_{2}\geq -M_2(1-y_1)\\
\end{array}$$
Così si ottiene il caso più generale con coefficienti anche negativi. Altrimenti

- trucco per JOB SEQUENCING:
![[Pasted image 20240203155751.png]]

## linearizzazione 
![[Pasted image 20240205102140.png]]
![[Pasted image 20240205102159.png]]
![[Pasted image 20240205102746.png]]


e per massimizzazione...
![[Pasted image 20240205102802.png]]

per il modulo
![[Pasted image 20240205102838.png]]
min w
w>= x
w >= -x


per min-max e max-min
![[Pasted image 20240205103141.png]]

# PLI

- zero half cuts



- gomory: esempio di esecuzione sull'ipad
no vabbe figata
pagina 10 di `Esercizi Da Altre Fonti`



- branch and bound


# dijkstra
![[Pasted image 20240205111619.png]]
Ricerca del cammino a costo minimo.

Notazione:
![[Pasted image 20240205111640.png]]


![[Pasted image 20240205111654.png]]
![[Pasted image 20240205111711.png]]s

all'inizio di ogni iterazione:
- elenca tutte le etichette (aggiornate + mai visitate) e seleziona quella minima => hai il nuovo nodo
- aggiorna le rimanenti dopo un forward star


# MST
## Kruskal
algoritmo greedy con criterio locale che non riconsidera.
esatto.
cerca l'albero ricoprente minimo (cioè tutti i nodi vanno toccati)

![[Pasted image 20240205120338.png]]![[Pasted image 20240205120412.png]]



## Prim
![[Pasted image 20240205120432.png]]