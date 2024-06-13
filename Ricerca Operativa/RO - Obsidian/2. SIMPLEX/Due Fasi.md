Di solito si parte dall'origine degli assi $\Rightarrow$ tutte le slack sono in base, e tutte le variabili originali sono fuori base, poste a zero.

Se l'origine degli assi non è una soluzione ammissibile, allora ci sono due casi:


## 1. La regione ammissibile non è vuota
.. ma non contiene l'origine. 
Bisogna trovare una soluzione iniziale alternativa per proseguire con il simplesso.
Si usa il **METODO DELLE DUE FASI**

Bisogna avere 
- problema in forma standard
- $b\geq 0$  (tramite opportuni cambi di segno)

### FASE UNO
Si costruisce il problema ausiliario.
![[Pasted image 20240125180238.png]]

- Aggiungere le variabili ausiliarie sporca il tableau. Dovrò riportarlo in forma canonica.

![[Pasted image 20240125180311.png]]

Metto in base le $y_i$ e risolvo per la nuova FO.
![[Pasted image 20240125180342.png]]
![[Pasted image 20240125180413.png]]

![[Pasted image 20240125180424.png]]![[Pasted image 20240125180452.png]]

Sappiamo che questa soluzione può essere sfruttata per il teorema di [stocazzo]
![[Pasted image 20240125180640.png]]

---

Interpreto l'ottimo $z*=0$ così:
![[Pasted image 20240125180614.png]]

---
![[Pasted image 20240125180750.png]]


### FASE DUE
Costruisco la base iniziale per il problema originale partendo dall'ottimo trovato nella fase uno.
![[Pasted image 20240125180716.png]]
![[Pasted image 20240125180722.png]]

## 2. La regione ammissibile è vuota
E quindi non c'è soluzione.