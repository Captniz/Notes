#telecomunicazioni

PDFs: 
\[[[1 Fenomeni ondulatori onde.pdf]]]
\[[[2 Effetto fotoelettrico.pdf]]]
\[[[3 Onde EM e Fotoni.pdf]]]
\[[[4 Mappa - Segnali e modulazioni.pdf]]]
\[[[5 Tecniche di trasmissione Analogiche e Digitali.pdf]]]
\[[[6 Tipi di Multiplazione di segnale.pdf]]]
\[[[7 Conversione A-D.pdf]]]
\[[[8 Bluetooth 1.pdf]]]
\[[[9 Bluetooth 2.pdf]]]
\[[[10 Banda ISM.pdf]]]

---
# Argomenti
Da studiare (Moodle): 
- Onde elettromagnetiche 
	- Punti 1 2 3  |  NO 4
- Tecniche di trasmissione 
	- Leggere prima la mappa concettuale 
	- Leggere il file "modulazione dei segnali" seguendo le indicazioni 
	- Sapere la differenza tra multiplazione di frequenza/tempo/codice
- Standard di comunicazione 
	- Caratteristiche principali del Bluetooth e del WIFI 
- Conversione A/D 
	- Sapere cos'è: campionamento, quantizzazione, codifica, teorema di Shannon, 
	- Sapere perché potrebbe servire il circuito di Sample/Hold in ingresso all'ADC

# Onde elettromagnetiche
## Fenomeni ondulatori
### La riflessione
**Quando un’onda incontra un ostacolo che ne impedisce la propagazione, essa viene riflessa, proprio come accade a una palla da biliardo quando urta contro una sponda.**

- La direzione di propagazione dell’onda forma un angolo con la perpendicolare alla superficie riflettente nel punto di incidenza.

![[Riflessione.png]]

- **Angolo di incidenza** (^ı) se si riferisce all’onda incidente.
- **Angolo di riflessione** (^r) se si riferisce all’onda riflessa.

### La rifrazione
**Il fenomeno della rifrazione si verifica quando l’onda attraversa la superficie che separa mezzi materiali diversi e consiste in un cambiamento della direzione di propagazione.**
Ciò è dovuto al fatto che quando cambia il mezzo, cambia la velocità di propagazione dell’onda ma la frequenza rimane la stessa, grazie all equazione: $λ * f = v$

![[Rifrazione.png]]

### La diffusione
**Quando l’onda incontra ostacoli con superfici irregolari, essa viene riflessa o rifratta un po’ in tutte le direzioni; questo fatto, nel caso di un’onda tridimensionale, determina il fenomeno della diffusione tutto lo spazio a disposizione.**

### La diffrazione
**La diffrazione è un fenomeno tipico delle onde e consiste nel fatto che il loro modo di propagarsi dipende dalle dimensioni dell’ostacolo che incontrano mentre si propagano in un mezzo.** 

- Quando le dimensioni dell’ostacolo sono piccole rispetto alla lunghezza d’onda si ha una deflessione delle linee di propagazione tale da consentire all’onda di aggirare l’ostacolo.
- Quando invece le dimensioni dell’ostacolo sono grandi la deflessione del fronte d’onda non è apprezzabile.

**Il fenomeno della diffrazione si può osservare anche quando l’onda incontra un ostacolo in cui è presente un varco.**

- Se la fenditura è grande in relazione alla lunghezza d’onda l’onda prosegue nella propria direzione.
- Se la fenditura è piccola, si osserva che i fronti d’onda si incurvano e producono un allargamento del fronte.

### La sovrapposizione
**Un’altra proprietà delle onde consiste nel fatto che quando due o più onde si incontrano in una regione dello spazio si ha la loro sovrapposizione.**
Nel caso di onde elastiche, l’ampiezza della perturbazione in ogni punto del mezzo è il risultato della sovrapposizione delle ampiezze delle onde che convergono in quel punto.

- Se la sollecitazione avviene nello stesso verso (in fase) l’ampiezza aumenta
- Se avviene nel verso opposto (opposizione di fase) l’ampiezza diminuisce e può anche annullarsi.

### L'interferenza
**Se abbiamo due sorgenti che producono onde di uguale ampiezza e frequenza che possono sovrapporsi, si osserva un fenomeno chiamato interferenza.**
I punti del mezzo in cui le onde sono in fase o in opposizione di fase rimangono sempre gli stessi e, di conseguenza, nel mezzo si osserverà l’alternarsi di zone in cui l’onda ha un’ampiezza molto grande con altre in cui lo è molto meno.

## Effetto fotoelettrico
**L'effetto fotoelettrico è quel fenomeno che consiste nell'emissione, da parte di un metallo, di elettroni quando viene investito da radiazione elettromagnetica avente una determinata energia.**
Scoperto da Heinrich Rudolf Hertz

Gli elettroni da espellere sono trattenuti all'interno da un' energia e per espellerli occorre investire il metallo con una radiazione elettromagnetica avente una energia $E = h · v$ almeno uguale all'energia che li trattiene. 

**La frequenza di tale radiazione viene detta frequenza critica v0** , ed è caratteristica di ogni metallo.

>![[Pasted image 20230515171549.png]]
>Utilizzando una luce di frequenza v > v0 , gli elettroni emessi mostrano una energia cinetica tanto più grande quanto maggiore è la frequenza v.

Questa scoperta, indusse la conferma che la luce potesse manifestare oltre che una **natura ondulatoria**, anche una natura **corpuscolare**. 
Solo particelle cariche di energia sarebbero in grado di spostare altre particelle e impartire loro un' accelerazione.

## Onde e fotoni
### Spettro Elettromagnetico e Spettro Visibile
**In fisica lo spettro elettromagnetico indica l'insieme di tutte le possibili frequenze o lunghezze d’onda delle radiazioni elettromagnetiche.**

Pur essendo lo spettro continuo, **è possibile una suddivisione puramente convenzionale ed indicativa in vari intervalli di lunghezze d’onda λ o bande di frequenza ν.** 

>$λ=c / ν$ 
>**$c$ = Velocità della luce nel vuoto**
>$v$ = **Frequenza**
>$λ$ = **Lunghezza d'onda**

![[Pasted image 20230515172329.png]]

Lunghezza d'onda:
- ***Luce visibile* <- λ -> *Onde radio*** -> **Scarsamente dannose** 
- ***Ultravioletto* <- λ -> *Raggi gamma*** -> **Dannose ( Ionizzanti )**

**Spettro visibile** -> Parte dello spettro elettromagnetico che cade tra il rosso e il violetto includendo tutti i colori percepibili dall'occhio umano (400 <--> 700nm & 770<-->430 THz).

### Fotoni
**Il fotone è una particella che ha vita infinita**.
- Può essere creato e distrutto dall’interazione con altre particelle, ma non può decadere spontaneamente. 
- Pur non avendo massa, è influenzato dalla gravità e possiede energia.
 Un fotone si comporta come un’onda quando si propaga nello spazio, mentre si comporta come particella quando interagisce con la materia.
- Ha natura ondulatoria e una natura corpuscolare.

Un atomo può emettere un’onda elettromagnetica solo quando un elettrone si trasferisce da un’orbita con energia maggiore $Ei$ a un’ orbita con energia minore $Ef$. L’energia dell’onda elettromagnetica emessa è: $E= Ei-Ef$.
Quindi la materia è in grado di emettere o assorbire energia raggiante solo sotto forma di pacchetti energetici.

**Una legge fondamentale della fisica quantistica dice che l'energia $E$ espressa in joule di un fotone di frequenza ν è:** 

$E = h*ν$
**$h = 6,624 * 10^{-34}$ -> Costante di Planck.**

# Tecniche di trasmissione

**Mappa concettuale:**
[[4 Mappa - Segnali e modulazioni.pdf]]

**Un sistema di trasmissione comprende:**
- *Trasmettitore*
- *Mezzo di trasmissione*
- *Ricevitore*

I segnali al suo interno subiscono **distorsioni e attenuazioni e vengono alterati dal rumore e da interferenze**.

**La scelta della tecnica di trasmissione è condizionata** principalmente dalla **distanza** a cui deve essere trasferita l’informazione, dalla **velocità di trasmissione richiesta** e dalle **caratteristiche del mezzo trasmissivo*:

- Per **distanze brevi**, spesso basta condizionare i segnali in modo da **garantire una sufficiente immunità al rumore.**
- **Per distanze lunghe** si usano tecniche di **modulazione e di multiplazione**.

## Modulazione
**Il processo di modulazione consiste essenzialmente nell’impiego di un segnale portante per trasferire il contenuto informativo di un altro segnale, detto modulante. Questo permette:**

- Trasmissione simultanea di più messaggi
- Adattamento ai mezzi trasmissivi

**La modulante modifica uno o più parametri (ampiezza, frequenza, fase) della portante con una legge precisa e definita.**

> *Modulante* + *Portante* = ***Segnale modulato*** -> *Demodulazione* = **Informazione**

### Tecniche di trasmissione
#### Modulazione analogica con portante armonica 
##### Modulazione di ampiezza (AM)

![[Pasted image 20230515175737.png]]

![[Pasted image 20230515175841.png]]

**L’indice di modulazione specifica di quanto la modulante incide sulla portante**.

![[Pasted image 20230515175908.png]]

**Per effetto della modulazione, il segnale $v_m (t)$ viene traslato in un campo di frequenze superiore.**

##### Modulazione di frequenza (FM)
![[Pasted image 20230515180349.png]]

![[Pasted image 20230515180410.png]]

##### Modulazione di fase (PM)

![[Pasted image 20230515180450.png]]

##### Modulazione ad ampiezza di impulsi (PAM)

![[Pasted image 20230515180543.png]]

![[Pasted image 20230515180654.png]]

![[Pasted image 20230515180707.png]]

![[Pasted image 20230515180744.png]]

##### Modulazioni PWM, PPM, PFM
![[Pasted image 20230515180958.png]]

![[Pasted image 20230515181024.png]]

##### Modulazione a variazione di ampiezza (ASK)

![[Pasted image 20230515181058.png]]

##### Modulazione a spostamento di frequenza (FSK)
![[Pasted image 20230515181144.png]]

##### Modulazione a spostamento di fase (PSK)
![[Pasted image 20230515181211.png]]

![[Pasted image 20230515181226.png]]

#### Modulazione digitale con portante armonica 
##### Modulazione a impulsi codificati (PCM)
![[Pasted image 20230515181331.png]]

## La multiplazione
### Multiplazione a divisione di frequenza FDM (Frequency Division Multiplexing)

- Il mezzo trasmissivo e' caratterizzato **da una banda di frequenze utilizzabili.**
- **La banda complessiva può essere divisa in sotto-bande cui associare un canale.**
- **Il segnale relativo** ad un canale viene trattato **mediante tecniche di modulazione in modo da associarlo a ciascuna sotto-banda.**

### Multiplazione a divisione di tempo TDM (Time Division Multiplexing)

- **Usata per segnali digitali.**
- **Dato un canale** numerico a **velocità $C (bit/s)$** si costruiscono **intervalli di tempo di canale (slot)** costituiti da **multipli del tempo di bit $t_b=1/C$**
- **Un canale (sorgente) può usare un intervallo di canale (slot) ogni N.**
- **Si definisce una struttura a trame consecutive costituite da N slot consecutivi.** 

### Multiplazione a divisione di codice CDM (Code Division Multiplexing)

- **La tecnica CDM consiste nel miscelare $N$ flussi di bit previa moltiplicazione di ciascuno di questi per una parola di codice $C_i$ scelta fra le $N$ parole di un codice ortogonale.**
- **Le parole del codice sono costituite da $N$ simboli binari, chiamati chip** per distinguerli dai bit di informazione, **di durata $N$ volte inferiore al bit di informazione. 

# Conversione analogico-digitale

**Campionamento** -> Prendere un valore del segnale analogico ogni tot
**Quantizzazione** -> Assegnare un quanto una variazione del segnale
**Codifica** -> Assegnazione di ogni quanto a un valore binario
**Teorema di Shannon** ->Se $fs$ è la frequenza di campionamento del **modulo S/H** ed $f_{max}$ è la frequenza massima del segnale da campionare, **il segnale in questione può essere ricostruito se è soddisfatta la condizione:**
$$f_{s}\ge 2f_{max}$$

**Risoluzione o Quanto** -> La minima variazione della grandezza analogica in ingresso che provoca una variazione di un LSB (Least Significant Bit)
 $$Q = \frac{V_{FS}}{2^n}$$
 
 $V_{FS}$ = **Tensione di fondo scala** ->tensione di riferimento fornita al convertitore che individua il massimo valore in ingresso convertibile in binario.

![[Pasted image 20230515185148.png]]

**Errore di quantizzazione** $\varepsilon_{max} =  \pm \frac{Q}{2}$  -> Errore massimo per arrotondamento a un valore digitale.

## Circuito sample & hold
**Sample and hold** e' un circuito che acquisisce la tensione di ingresso in un determinato istante (**campionamento**) e la mantiene invariata all'uscita fino ad una nuova lettura.

Il circuito S/H non è sempre indispensabile, la sua presenza dipende dalla velocità di variazione del segnale da convertire.

# Standard Bluetooth e WIFI
## Bluetooth
**Bluetooth è uno Standard Aperto per telecomunicazioni wireless (trasferimento di dati e voci) a corto raggio.**

- Bluetooth è stata sviluppato nel 1994
- Lo standard Bluetooth serve a realizzare le cosiddette Personal Area Network (PAN), cioè piccole reti dell’estensione tipica di qualche metro
- Bluetooth funziona in banda ISM 2.45 GHz
	- In telecomunicazioni la banda ISM (Industrial, Scientific and Medical) è il nome assegnato dall'Unione Internazionale delle Telecomunicazioni (ITU) ad un insieme di porzioni dello spettro elettromagnetico riservate alle applicazioni di radiocomunicazioni non commerciali, ma per uso industriale, scientifico e medico.
- Con una modulazione frequency hopping – spread spectrum per ridurre l’effetto di interferenze e fading
- Tipicamente, un canale radio fisico è occupato da più dispositivi sincronizzati su una stessa sequenza di frequency hopping. Tale insieme di dispositivi si chiama “piconet”. Un dispositivo, detto “master”, è responsabile della sincronizzazione. Gli altri sono “slave”
- Lo standard è pensato per essere a basso costo
- Una rete di Bluetooth è organizzata in strati (livelli). Sopra al canale radio fisico abbiamo una serie di canali e collegamenti (link), e i relativi protocolli. Partendo dal canale radio fisico, abbiamo il livello fisico, composto dal canale fisico (physical channel) e dal collegamento fisico (physical link), il livello logico, composto dal trasporto logico (logical transport) e da collegamento logico (logical link), poi il livello “L2CAP”.

## WIFI 
**Wi-Fi è un insieme di tecnologie per reti locali senza fili (WLAN) basato sugli standard IEEE 802.11, il quale consente a più dispositivi  di essere connessi tra loro tramite onde radio e scambiare dati.**

- I dispositivi compatibili Wi-Fi possono connettersi a Internet tramite una WLAN e un punto di accesso wireless
- Con la tecnologia disponibile al 2017, un access point (o un hotspot) all'interno di un edificio può avere una portata di circa 20 metri (il segnale a onde radio è attenuato dai muri), mentre all'esterno può coprire un raggio di circa 100 metri e, usando più punti di accesso sovrapposti, anche di diversi chilometri quadrati.