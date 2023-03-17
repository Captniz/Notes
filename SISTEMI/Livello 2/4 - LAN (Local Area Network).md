#sistemi #livelloDue 

PDF: \[ [[10 - LAN.pdf]] ]

---

## La LAN
**La LAN** è uno **standard** di sistema di comunicazione che permette ad un insieme di nodi di comunicare con alta velocità, basso tasso di errore ma area limitata; è presente a livello 1 e 2.

Caratteristiche:
1. Supporto per protcolli a canale condiviso.
2. Canale di tipo broadcast.
3. Disponibilità di sistema per comunicazioni unicast.

### Classificazione di reti cablate
> In base al canale di trasmissione:
- **Bus**
- **Anello**
- Altre ...

> In base al mezzo trasmissivo
- **Ethernet**
- **Fibra ottica**
- Altre ...

> In base alla modulazione
- **Banda base**
- **Banda larga**

> In base alla tipologia di protocollo
- **Su domanda**
- **Casuale**

## Standard IEEE 802
Usato su reti LAN, questo protocollo **divide a metà il livello 2**:
- **LLC**   | Alto livello
- **MAC** | Basso livello

Ci sono diversi tipi di questo standard:
- **802.3** -> Ethernet | CSMA / CD
- **802.5** -> Token Ring
- **802.11** -> Wifi

### MAC - Media Access Control
Regola **l'accesso al canale condiviso** e effettua **l'incapsulamento più esterno**.

Caratteristiche:
- Non confermato
- Non connesso
- Controllo parziale dell'errore
- No frammentazione
- No consegna in sequenza
- Indirizzo di 6 byte unico per ogni scheda di rete (`FF FF FF FF` : Indirizzo di broadcast)

#### Incapsulamento di una PDU nel MAC
- <mark style="background: #F85552AA;">Header</mark>
- <mark style="background: #8DA101AA;">Payload</mark>
- <mark style="background: #DFA000AA;">Trailer/Tail</mark>

<mark style="background: #F85552AA;">[PREAMBOLO][DESTINATION][SOURCE][TYPE]</mark><mark style="background: #8DA101AA;">[PAYLOAD]</mark><mark style="background: #DFA000AA;">[CRC]</mark>

| Campo       | Dimensione   | Descrizione                  |
| ----------- | ------------ | ---------------------------- |
| Preambolo   | 8 Byte       | Sincronizzatore per stazioni |
| Destination | 6 Byte       | MAC destinatario             |
| Source      | 6 Byte       | MAC mittente                 |
| Type        | 2 Byte       | Protocollo livello superiore |
| Payload     | 45-1500 Byte | PDU Livello superiore        |
| CRC         | 4 Byte       | Cyclic Redundancy Check      | 

### LLC - Logical Link Control
**Maschera i dettagli della LAN** ai livelli superiori.

Caratteristica principale:
> Si comporta diversamente a seconda del tipo di comunicazione richiesta dal livello superiore.

**LLC1**
- Non confermato
- Non connesso
- No frammentazione
- No controllo errori
- No consegna in sequenza

**LLC2**
- Confermato | **Go Back N** , N->127
- Connesso
- Controllo errori
- Consegna in sequenza
- No Frammentazione

**LLC3**
- Confermato | **S&W**
- Non connesso
- Controllo errori
- Consegna in sequenza
- No frammentazione

#### Incapsulamento di una PDU nel LLC
- <mark style="background: #F85552AA;">Header</mark>
- <mark style="background: #8DA101AA;">Payload</mark>

<mark style="background: #F85552AA;">[DSAP][SSAP][CONTROL]</mark><mark style="background: #8DA101AA;">[PAYLOAD]</mark>

| Campo       | Dimensione   | Descrizione                  |
| ----------- | ------------ | ---------------------------- |
| DSAP   | 1 Byte       | Destination Service Access Point (Punto del lv.3 del destinatario) |
| SSAP | 1 Byte       | Source Service Access Point (Punto del lv.3 del mittente)|
| Control      | 1 Byte       | Gestisce conferma e sequenza                 |


### IEEE 802.11 - WiFi
Nato nel **1997** basati sulla frequenza **2.4Ghz**, utilizzata per ragioni legali. La più nuova **5Ghz** è più veloce ma anche più soggetta alle distanze.

Una rete WiFI è composta da più dispositivi hardware:
- **Wirless terminal**
󰘍 Dispositivi mobili.
- **Access point** 
󰘍 Consentono ai **WT** di collegarsi alla rete WiFi; spesso sono anche dei bridge che gestiscono la rete cablata. Più **AP** collegati a una rete cablata formano un **Wirless distribution system.**

#### Problemi del WiFi
**Ci sono due principali problemi noti dello standard WiFI.**
###### Problema della stazione nascosta
>Quando due stazioni stanno comunicando con una terza, ma si trovano fuori dal loro raggio di azione ( **A** -> **B** <- **C** | **C** non vede **A**), trovano il canale libero e iniziano una trasmissione; mandando insieme un messaggio creano una collisione.

###### Problema della stazione esposta
>Quando due paia di stazioni comunicano tra di loro si ha la possibilità che si interromano le trasmissione poichè una coppia sente il canale dell'altra che è impegnato in una comunicazione e lo scambia per il proprio, impedendo la comunicazione ( **A** -> **B** , **C** -> **D** |  **A** sente la comunicazione in corso di **C**). 