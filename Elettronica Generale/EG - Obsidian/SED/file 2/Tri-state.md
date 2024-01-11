## Problema
Vedi in [[Stadio di uscita dinamico#Problema AO]]

**IDEA**: si pensa dunque di creare degli stadi di uscita appositi.. ad esempio si prevede uno stato di *alta impedenza* che ci permetta di sfruttare una R di pull up debole e quindi sminchiare di meno i livelli.

## Soluzione
Uno [[Stadio di uscita dinamico|stadio di uscita speciale]]. 
Aderisce sempre al modello $I_{oh}\,I_{ol}\,V_{oh}\,V_{ol}$ con $T_{rise}$ e $T_{fall}$.
![[Pasted image 20231111181925.png]]

*Descrizione*: può funzionare anche con entrambi gli interruttori di uscita spenti (il terzo stato = "Z" = stato ad alta impedenza): quindi le uscite possibili sono "0", "1" e "Z". 

CONDIZIONI:
- E' necessario avere un ingresso di controllo.
- Serve una RES di *pull-up* per fissare il valore della linea quando il dispositivo ha uscita "Z"

**Svantaggio**: la logica di controllo degli switch rende il dispositivo lento!

*Nota*: la resistenza di pull up in questo caso (!= da XTL) non serve a ricreare alcun livello, solo a tenere l'entrata dell'uscita determinata.


---

ATTENZIONE:
Le linee multiutente realizzate con 3-state necessitano di un *protocollo perchè solo un'uscita alla volta può essere abilitata*!
![[Pasted image 20231111181936.png]]

---
Questo dispositivo può emulare il funzionamento dell'[[Open Collector]] (ovvero uscita "Z")
- IN="0" + !CONTROL
- IN=X + CONTROL
![[Pasted image 20231112184429.png]]

---
![[Pasted image 20231112194231.png]]