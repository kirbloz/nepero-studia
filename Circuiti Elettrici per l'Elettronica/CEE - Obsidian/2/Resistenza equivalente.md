## 1. Metodo del generatore arbitrario
- Si spengono tutti i generatori indipendenti 
- Si collega al bipolo un generatore che impone una grandezza $i_0$ o $v_0$
- Si calcola l'altra $v_x$ o $i_x$
$$\large R_{eq} = \frac{v_x}{i_0} = \frac{v_0}{i_x}$$
E' utile imporre la grandezza nota $=1$ per semplificare di molto i calcoli.
>Ha senso usarlo quando il bipolo è complicato e voglio sfruttare un metodo sistematico.
## 2. Calcolo diretto
- Si chiude il bipolo su di un generatore indipendente di corrente $i_0$ arbitrario
- Si ricava la tensione $v_x$ ai morsetti del bipolo (che poi sono gli stessi a cui ho collegato il generatore)
- La relazione sarà obbligatoriamente nella forma:
$$ \large v_x = R_T \, i_0 + v_T$$
Si ottengono $v_T$ ed $R_T$ per thevenin tutti insieme.

## 3. Thevenin e Norton
- Si ricava $v_T$ dall'equivalente Thevenin del bipolo
- Si ricava $i_N$ dall'equivalente Norton del bipolo
- Si calcola quindi: 
$$ R_T= \frac{v_T}{i_N}$$
Non molto utile: non lo posso usare se il circuito è privo di generatori indipendenti