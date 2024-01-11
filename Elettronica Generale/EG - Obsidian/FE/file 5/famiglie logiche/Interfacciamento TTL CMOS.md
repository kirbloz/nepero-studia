Supponiamo una $V_{p}=5V$
![[Pasted image 20231102094708.png]]

- Se un *TTL* pilota un ricevitore *CMOS* non si rispettano le condizioni di immunità al rumore.

![[Pasted image 20231102100222.png]]

Si sfrutta una resistenza di pull-up $R_{p}$ che rispretta i seguenti valori
      $\large R_{p,max} = \frac{V_{cc}-V_{oh}'}{N\cdot I_{ih}}$
      $\large R_{p,min} = \frac{V_{cc}-V_{ol}'}{I_{ol}-N\cdot I_{il}}$

Questa resistenza *interdice* il totem-pole (tiene T4 sempre OFF)

**PROBLEMA**
Dimensionare $R_{p}$ tra TTL-CMOS se ci sono 5 carichi CMOS con immunità al rumore in "1" a $V_{nh}=0.2V$
Dati:
         $N=5$
         $V_{nh}=0.2V$

La $R_{p}$ serve a <span style="background:#fdbfff">fornire corrente</span> agli $N$ carichi <span style="background:#fdbfff">senza "caricare" il transistore dello stadio di uscita</span> (effetto open collector).

"1": 
$V_{oh}'=V_{ih}(CMOS)+V_{nh}=3.7V$
$(V_{cc}-V_{oh}') / R_{p} \geq N\cdot I_{ih}=260 k\Omega$

"0":
$V_{ol}=V_{ol} (TTL)$ e $I_{ol}=I_{ol}(TTL)$
$N\cdot I_{il}=$ corrente totale dei carichi (5muA)
$N\cdot I_{il}+ (V_{cc}-V_{ol}) / R_{p} < I_{ol}$

$R_{p,min}=(V_{cc}-V_{ol}) / (I_{ol}-N\cdot I_{il})$
=...=563