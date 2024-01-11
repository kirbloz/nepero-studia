Questi cosi sono poco usati.
Necessitano di uno *stadio di sincronizzazione* a valle (4 FF con clock comune e Qi in ingresso) per eliminare lo skew rate e gli stati spuri dovuti a disallineamenti parziali.

- Nel caso di clock attivo sul fronte di discesa si ha un contatore down (cioè conta da max a 0)
![[Pasted image 20231205233548.png]]

I singoli FF sonoo configurati così:
![[Pasted image 20231205233615.png]]
Ognuno di loro è un piccolo contatore ad 1 bit. Si chiama anche *divisore di frequenza* (praticamente "conta i fronti attivi")

**PROBLEMA**:
per i contatori asincroni con tutti i clock diversi si rischia un disallineamento temporale delle uscite (problema skew(??) boh cercherò su wikipedia) per cui le uscite non commutano assieme!
Dunque potrebbe esistere un momento (anche piccolissimo) tra il commuting di un FF e un altro, in cui si assume uno stato "illegale" => *stato spurio*. Questi vanno filtrati.

La soluzione è sincronizzare tutti allo stesso clock. 
Vedi [[Contatore|Contatore sincrono]].