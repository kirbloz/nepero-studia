Generalmente quando si parla di sistemi digitali si hanno tre momenti: *acquisire* gli ingressi e le informazioni, *elaborazione*, e *generare* le uscite.

### Ingressi e Uscite
Questi due sono gli stadi a contatto con il mondo il esterno. 
I segnali sono normalmente gestiti mediante dispositivi periferici; il loro lavoro è gestirne i vari tipi, le compatibilità.

I *segnali digitali* possono essere:
1. **statici**, informazione binaria fissa. Non importa in che momento leggo il bit.
2. **time coded**, l'informazione è codificata nel tempo. Dipende quindi dalla durata dell'impulso $T_{on}$, dal periodo dell'onda $T_{on}+T_{off}$, dal duty cycle $T_{on}/T$, dallo sfasamento tra due segnali etc..

Possiamo avere anche un'altra categorizzazione dei segnali:
- **codificati**, quelli usati dalle interfacce seriali (UART, SPI, USB, BT...)
- **analogici**, l'informazione è numerica, in un range da 0 a $N=2^n$.

## Segnali analogici
A cosa servono? 
- Controllo e regolazione di sistemi (genero un certo valore $u(t)$nel tempo per ottenere un certo output $e(t)$ desiderato)
- Per stimare o misurare o trasferire info $e(t)$
- Generare stimoli $u(t)$

Ogni singolo blocco qui sotto introduce del rumore di *quantizzazione* $n_i(t)$ e un ritardo $t_i$ dovuto alla propagazione+elaborazione.
![[Pasted image 20231209110450.png]]

- Dopo lo stadio $t1$ non ho più segnali codificati nel tempo - A - bensì una sequenza di valori - D.

Lo stadio 0 si usa per del <span style="background:#b1ffff">fine-tuning del segnale analogico</span> in arrivo, perchè a volte i sensori emettono segnali terribili da digerire. Come si fa?
-  Si usa un [[AO]], necessario per adattare i segnali al range di acquisizione. Svolge un'operazione di *regolazione del guadagno*.
- Si usa un [[Sottrattore Invertente|sottrattore]] o [[Sommatore|sommatore]] per regolare l'offset. Svolge un'operazione di *compensazione offset*.
- Si usa un filtro, di solito un *passa-basso*.
>Nei segnali audio invece passa-alto.. dipende dall'applicazione.

Per gli stadi intermedi vedi [[Elaborazione Analogica]].

Lo stadio 4 (finale) si usa invece per<span style="background:#b1ffff"> riadattare il segnale </span>alla rete elettrica a cui è collegato il sistema, o counque ai dispositivi successivi che leggeranno i segnali emessi.

---

*Nota sui filtri*: Perchè devo praticamente sempre tagliare le frequenze alte? Dal TH di Shannon.
Se si passa dal mondo del tempo continuo a quello discreto, la frequenza di campionamento deve essere *almeno doppia* rispetto alla massima frequenza raggiunta dal segnale stesso.
Quindi se la $f_{max}$ è già esagerata di suo, diventa complicato campionare in maniera efficace.

>Si chiama **aliasing** la degenerazione del segnale quantizzato.

![[Pasted image 20231209111725.png]]![[Pasted image 20231209111737.png]]

Molto impiegati sono anche i sistemi retroazionati: ovvero che si autoregolano un qualche valore letto da un sensore con azione tempestiva (rispetto alle costanti di tempo del sistema).