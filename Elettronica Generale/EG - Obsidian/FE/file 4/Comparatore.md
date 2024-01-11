Un amp. con guadagno elevatissimo è modellizzato come un *comparatore* ossia la tensione di uscita è nel range con estremi i valori di alimentazione. E' un dispositivo digitale.

#### Configurazione
La *configurazione* da comparatore si realizza collegando $V_{in}$ al pin per $V_{+}$ e GROUND al pin per $V_{-}$ $\Rightarrow$ reazione positiva. (cioè a isteresi, unico che studiamo). Si dice che l'AO lavora in **Saturazione** (sufficiente avere un $V_{id}$ superiore ai millivolt).

Si utilizza la doppia alimentazione, che è anche il riferimento per codificare l'<span style="background:#b1ffff">uscita digitale</span>. Vedi [[#Segnali in uscita]]

#### Modello circuitale
![[Pasted image 20231025000546.png]]
> I morsetti $+$ e $-$ sono simmetrici
#### Caratteristiche
Osserviamo il grafico caratteristico dell'AO: ![[Pasted image 20231025000622.png]]
E' chiaro che basta una poco meno che minima differenza tra gli ingressi $V_{+}$ e $V_{-}$ perchè il comportamento non sia più lineare ma "venga sbattuto agli estremi" del range di alimentazione $\Rightarrow$ *(una piccola tensione positiva viene amplificata a $+V_{cc}$ e una piccola tensione negativa va a $-V_{cc}$)

#### Segnali in uscita
L'AO come comparatore può solo dare due valori in OUT: $\pm V_{p}$ 
$\Rightarrow$ La doppia alimentazione ci permette di realizzare un ottimo comparatore con uscita digitale
$$\begin{align} +V_{cc} = +5V \quad \rightarrow \quad \text{alto, "1"}\\ -V_{ee} = -5V \quad \rightarrow \quad \text{basso, "0"} \end{align}$$


Per il comportamento in uscita nel caso della REAZIONE POSITIVA vedi [[Comparatore con Isteresi#Segnali in uscita]] perchè c'è da fare un ragionamento con il rumore.

>Nota: è come se avessi un amplificatore a guadagno altisismo => il guadagno massimo che posso avere non è mai maggiore dell'alimentazione.
#### Problema del rumore
Avendo una regione lineare molto ristretta - l'AO supporta delle MINIME differenze di tensione tra morsetti - il rumore magnetico diventa un problema.

NOTA: questo è il motivo per cui non si usa mai il comparatore secco e nudo, per la sua sensibilità al rumore.
>Se V+ è piccolo, basta poco rumore per continuare a commutare e osservare segnali in uscita completamente inutili. Guasti.
>ESEMPIO: Se ho IN una sinusoide a bassa frequenza, basta poco rumore a sputtanare tutto.