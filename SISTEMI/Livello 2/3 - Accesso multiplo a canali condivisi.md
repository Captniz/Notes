#sistemi #livelloDue

PDF: \[ [[9 - Accesso multiplo a canali condivisi.pdf]]]

---

## Comunicazione sui canali condivisi

> [!warning]- Canale Condiviso
> 
**Mezzo di comunicazione** utilizzato da 2 o più **entità** che possono ricevere e trasmettere contemporaneamente.

### Problematiche
**Nel caso due o più nodi trasmettano contemporaneamente si creano delle interferenze (*Collisioni*).**

In base alle soluzioni possiamo distinguere i vari protocolli.

### Tipologie
**BUS:**
- Bus centraliazzato
- Bus distribuito

**RING:**
- Ring centralizzato
- Ring distribuito

\[[[Accesso multiplo a canali condivisi 2023-03-07 16.25.42.excalidraw|Disegno]]]

### Efficienza media
**Valore di quanto è sfruttata una rete.**

L'efficienza è compresa tra 0 e 1 ( $0 < E < 1$ ), quindi moltiplicando per 100 otteniamo la percentuale di sfruttamento della rete. 

>  $E = \frac{T}{C}$

- **E** ->  Efficienza media
- **C** -> Capacità canale
- **T** -> Traffico medio

### Protocolli di accesso al canale
#### Protocolli ad assegnamento prefissato
**Protocolli che suddividono il canale in sotto canali nel dominio del tempo, frequenza o codice.**

Protocolli:
- **TDMA** | Time Division Multiple Access
- **FDMA** | Frequency Division Multiple Access
- **CDMA** | Code Division Multiple Access

###### TDMA
**Definizione**
>Si suddivide l'asse del tempo in finestre assegnate a un nodo, ogni finestra ha tempo **T**. Tra ogni cambio di finestra è presente un tempo **G** detto di guardia, questo assicura che i bit arrivino tutti al destinatario. 

**Vantaggi**
󰘍 Si evitano collisioni, **molto democratico**.

**Svantaggi**
󰘍 Inefficiente con tanti nodi collegati alla rete.

###### FDMA
**Definizione**
> Si suddivide l'asse delle frequenze in finestre assegnate a un nodo, ogni finestra ha frequenza. Tra ogni cambio di frequenza è presente un salto detto di guardia, questo assicura che anche sforando la frequenza non si trasmettano ad altri canali. 

**Vantaggi**
󰘍 Si può trasmettere quando si vuole.

**Svantaggi**
󰘍 Ogni stazione ha a disposizione un numero limitato di frequenze stabilito dal protocollo, che varia in base ai nodi collegati.

###### CDMA
**Definizione**
> La trasmissione di una stazione viene integrata con una sequenza detta di **Chipping**. Questa sequenza è pseudocasuale e viene usata per minimizzare le interferenze. 

**Obiettivo**
󰘍 Minimizzare l'uso di banda e di tempo

#### Protocolli ad assegnamento su domanda 
**Protocolli con l'obbiettivo di minimizzare lo spreco di banda e tempo nell'assegnare la comunicazione a nodi che non devono trasmettere.**
Questi protocolli funzionano tramite un messaggio inviato quando un nodo vuole trasmettere, chiamato **messaggio di polling**.

> [!warning]- Polling e Interrupt
> **Polling:** Controlli continui in attesa di un messaggio.
> **Interrupt:** Il messaggio arriva quando è il momento di comunicare.

Il **messaggio di polling** viene inviato solo quando il canale è libero. Un nodo per liberare il canale, una volta che iniziata una comunicazione, deve mandare un byte speciale.

Protocolli:
- **Roll Call Polling**
- **Hub Polling**

###### Roll Call Polling
**Usabile solo su canali centralizzati.**
**Il controller assegna l'autorizzazione a comunicare a turno, e ogni volta quando termina riprende il controllo della comunicazione. **

###### Hub Polling
**Usabile solo su reti ad anello.**
**L'autorizzazione a trasmettere viene passata di volta in volta al nodo successivo; questa autorizzazione è sotto forma di codice chiamato token.**

#### Protocolli di accesso casuale al canale
**Questi protocolli sono segnati con l'assenza di segnalazione per coordinare la comunicazione.**

Principi di base:
1. Un nodo può trasmettere quando vuole.
2. I protocolli possono aggiungere vincoli extra.
3. Si deve prevedere le eventuali collisioni

> [!warning]- Rilevamento di una collisione
> E' avvenuta una collisione quando:
> - L' **ACK** di lv. 2 non torna.
> - I nodi trasmettono e ascoltano allo stesso tempo, se il pacchetto letto è uguale a quello trasmesso non ci sono porblemi, altrimenti è avvenuta una collisione. (*Listen* ***while*** *talking*)


Protocolli:
- **Pure ALOHA**
- **Slotted ALOHA**
- **CSMA / CD** | Carrier-Sense Multiple Access / Collision Detection

###### Pure ALOHA
**I nodi trasmettono a piacere, in caso di collisione si eliminano entrambi i pacchetti e entrambi i nodi riprendono la comunicazione dopo un tempo casuale.**

###### Slotted ALOHA
**Variante della versione precedente; si suddivide l'asse del tempo in slot e i nodi possono iniziare a comunicare solo dall' inizio di uno slot.**

###### CSMA / CD
**I nodi prima di trasmettere ascoltano che il canale sia libero** (*Listen* ***before*** *talking*) **e se lo è trasmettono.**

In questo protocollo l'unico modo in cui si potrebbe verificare una collisione è nel caso un nodo non faccia in tempo a leggere il messaggio di un altro nodo a causa del **ritardo del canale**.

Il nodo che rileva una collisione smette di trasmettere e invia il segnale di interruzione sul canale, detto **segnale di jamming**.
La comunicazione riprende dopo un tempo casuale e si ritenta al massimo 16 volte.