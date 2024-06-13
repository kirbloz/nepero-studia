Questo metodo è una procedura algebrica; tutti i concetti che stanno alla base sono di natura geometrica.
Per i concetti vedi in [[PL]]
### POV ALGEBRICO
Il simplesso parte da una soluzione di base ammissibile (iniziale)
Poi passa ad una nuova soluzione (operazione di pivoting, scambia var in base)
Ripete 

### POV GEOMETRICO
Parte da un vertice della regione ammissibile
Passa ad un nuovo vertice (migliora il valore della FO) adiacente allo scorso
Ripete

# Complessità
![[Pasted image 20240125184446.png]]

# Casi particolari
![[Pasted image 20240205110950.png]]

## Soluzione illimitata

Vedi [[Soluzioni#Soluzione illimitata]]

- una colonna (variabile) ha tutti valori negativi => il suo valore può crescere all'infinito
- nel tableau non posso scambiare qualcosa che ha pivot negativi, quindi per bilanciare le altre var pistano via
- un'equazione contiene due variabili con segno discorde => i loro valori si equilibrano crescendo in direzioni opposte! 
- FO ha direzione ortogonale (gradiente) alla direzione di apertura del poliedro
## Soluzione ottima multipla

Vedi [[Soluzioni#Ottimo multiplo]]
![[Pasted image 20240125182308.png]]
corrisponde a $\Delta f =0$ , nessuno spostamento nella FO. Bensì $\Delta x_{k}\neq 0$, perchè si trovano effettivamente più soluzioni! Con ovviamente $c_k=0$

- la FO è parallela ad un vincolo => arriva a coincidere con una frontiera per un pezzo => due vertici => infiniti punti ottimi
- nella tabella ottimale trovo una *variabile fuori base con coefficiente nullo* => questa var può cambiare senza modificare la FO => trovo tanti punti per lo stesso valore ottimale!
- tableau con ottimo multiplo => $\exists\,\, c_{k}=0 \, | x_{k}\in x_N$   

esempio
 ![[Pasted image 20240125183432.png]]



## Soluzione ottima degenere
Vedi [[Soluzioni#Soluzioni Degeneri]]
![[Pasted image 20240125184119.png]]

Si riconosce una soluzione degenere quando $x^t=[x_B\,;x_N]$ ha *almeno una componente in base* non positiva, ma $x_{Bi}=0$.
Significa che la base è rappresentata da meno di $n-m$ equazioni indipendenti, cioè fissa almeno una variabile a zero in più


In termini di simplesso..
![[Pasted image 20240125183944.png]]
esce una variabile con valore nullo => dovrà entrarne una con valore nullo.
Una variabile a zero implica che non c'è una qualche quantità da giocarsi con altri vincoli quando si cambia base: il vertice identificato rimane lo stesso!
- si può degenerare con CCR positivi, negativi o nulli.

- se $c_k=0$ allora $\Delta f= 0\cdot x_k$ per cui anche se $x_k$ diventasse positiva, non cambio FO, non cambio vertice, ma ho effettivamente una base con composizione diversa. soluzione multipla!