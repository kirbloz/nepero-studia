#### Ritardo
![[Pasted image 20231031221833.png]]
Una nota importante va fatta sul ritardo di propagazione dell'informazione: le porte logiche non lavorano istantaneamente, per cui esiste un ritardo tra la variazione del segnale IN e la variazione conseguente del segnale OUT. 

Serializzando più porte logiche, questo ritardo va a sommarsi.
>Roba riguardante il Fan-Out

---
#### BJT
Il ritardo è un fattore che si analizza quando si studia il modello dinamico delle funzioni logiche.
E' un problema quando si sfrutta la tecnologia del BJT, perchè nel momento in cui io porto la base a potenziale nullo $V_{b}=0$, non c'è subito un cambio $I_{c}\rightarrow0$. 
=> C'è appunto un *ritardo*, che fa sembrare il mio componente *sordo*.
E' dovuto al fatto che la <span style="background:#b1ffff">base deve scaricare i portatori maggioritari rimasti</span>.
=> Solitamente si aggiunge una resistenza-GND in parallelo prima di B per dare un percorso di scarica il più immediato possibile.