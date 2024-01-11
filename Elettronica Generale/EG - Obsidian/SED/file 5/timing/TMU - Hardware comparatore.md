### Hardware comparatore 
Ricordo a cosa serve l'attività del comparatore nella TMU:
"Voglio generare segnali che commutano in un momento preciso"
>Esempio: quando $T_{FR}$ vale 1000HEX, output 1.

L'architettura dunque è forzante e si schematizza così
![[Pasted image 20231209105019.png]]

- Deve esserci una struttura SET-RESET per potere forzare l'uscita "quando vogliamo" = il quando vogliamo sarà allo scatto del comparatore (cioè ha trovato una corrispondenza)

Come funziona?
Immagino che il counter conti come suo solito. Ad ogni conteggio pone in A il suo stato corrente.

Il registro memorizza il valore desiderato, cioè il momento in cui vogliamo che scatti il comparatore: nel nostro caso 1000HEX.
Il dato sarà sempre disponibile in B.

Il comparatore ad ogni aggiornamento farà il controllo:
	A == B ?
Quando trova la corrispondenza scatta l'uscita che resetta il FF di flag e mette un 1 in entrata al registro collegato al FF di OUT (anti metastabilità).

---

*Nota*: il microcontrollore ha una mappa di memoria + REG di configurazione per stabilire su quali indirizzi si avrà input, quali output, flags, clock etc.. 
Ma i 3-state sono fichi perchè li puoi programmare a livello SW senza fare specifiche HW "dure" (il PIN_MODE)
![[Pasted image 20231209105327.png]]

