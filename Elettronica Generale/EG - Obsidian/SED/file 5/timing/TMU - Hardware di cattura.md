### Hardware di cattura
L'architettura si schematizza così
![[Pasted image 20231209104225.png]]

DEF :
 si chiama *accumulatore*
 un dispositivo costituito da un registro interfacciato ad un bus dati.

Il registro è basato su un funzionamento a Flip Flops con lo stesso clock. Campiona e memorizza in Q lo stato D quando CLK sale da 0 a 1.

#### Problema
"Voglio che il segnale REG campioni il valore IN solo quando c'è CLK, perchè non posso portare l'uscita del contatore direttamente all'ingresso del registro"

Soluzione:
 Con riferimento alla figura sopra: aggiungo un FF per evitare la metastabilità dovuta alla commutazione dello stato del counter in contemporanea al clock.

*Nota*: perchè realizzo una soluzione hardware e non software? Perchè l'attività di attesa è 100% bloccante!
E le attività bloccanti entrano in conflitto con gli interrupts: si generano errori anche gravi.
![[Pasted image 20231209104824.png]]

---
Qua sotto ho spiegato praticamente la stessa cosa ma un po' più verbosa.

![[Pasted image 20231209102455.png]]

Se immaginiamo di avere solo la circuiteria disegnata in blu, in teoria potrebbe funzionare tranquillamente.
Ovvero il counter fa il suo dovere, calcola il suo tempo.. e solo quando l'ingresso al registro "va su" allora si cattura l'uscita del contatore.
*Ma e se il REG leggesse esattamente mentre Counter cambia stato? Metastabilità!*
La soluzione può essere quella di:
1. prevedere uno stadio di SYNC
2. fare sì il REG vada a 1 non sul frontre d'ingresso ma sull'ingresso sincronizzato
>Posso lavorare su fronti di salita/discesa per evitare ste cose

---

Vediamo la soluzione disegnata sopra:
- Il clock entra sia nel counter - per le solite attività di timer free-running - e nel Flip Flop
- Il dato nel Flip Flop è collegato ad uno XOR programmabile
  >Bit fisso a 1 implica di leggere quando si verifica livello alto, a 0 quando si verifica livello basso.
- L'uscita del FF è collegata al clock del registro, per cui SOLO QUANDO il FF emetterà un 1 allora il registro leggerà il valore che il counter gli ha preparato in ingresso! 
Ora funziona siuuu