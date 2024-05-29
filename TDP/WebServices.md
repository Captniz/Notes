---
tags:
  - tdp
---
## Definizione
> E' frequente la necessità di far comunicare tra loro sistemi **software diversi**. In generale non è possibile **trasferire dati direttamente in formato binario tra software eterogenei**, poichè diversi linguaggi di programmazione implementano i tipi di dati in modo diverso.

Per far questo si usano i **Web Services**

> [!caution] WS
> **Un web service (ws)** è un sistema software che offre un
servizio rivolto ad un altro sistema software, utilizzando gli
stessi protocolli e tecnologie utilizzati dal World Wide Web
(HTTP e HTTPS)

## Soluzioni

Un'altro problema di cui tener conto quando si trasmettono dati
in binario dall'**ordinamento dei byte** ( *Big endian / Small endian* ).

Per far comunicare due software eterogenei (A e B) sarebbe
utile disporre di un sistema standard che consenta di invocare,
dal codice dell'applicazione A, una funzione dell'applicazione B,
come se si trattasse di una chiamata locale.

> [!note] RPC
> **Remote Procedure Call** invocazione da parte di un
programma di una funzione (o metodo) attivata su un
computer diverso da quello su cui il programma è in
esecuzione. Nella pratica la chiamata remota è realizzata tramite l'invio di
una richiesta ad un server.

> [!note] Marshalling
> **Marshalling** -> Conversione dei parametri in un formato condiviso tra
chiamante e chiamato, adatto al trasporto attraverso la rete.
**Unmarshalling** -> Attesa e ricezione del valore di ritorno, riconversione del
valore di ritorno nel formato del chiamante.

Un fattore chiave della trasmissione sulla rete attraverso WS sono gli **standard semplici e condivisi**.

Tecnologie per la creazione di RPC:
- **Java RMI** ( *Remote Method Invocation* )
	- Consente di invocare un metodo su una JVM remota.
	- **Limitazione**: le due applicazioni comunicanti devono essere scritte entrambe in Java
- **DCOM** ( *Distributed Component Object Model* )
	- Soluzione proposta da Microsoft, solo per Windows (ora superata da .NET)

## Risposte

Al contrario di web applications o web sites, le risposte dei
WS sono progettate per essere utilizzate da un altro software,
anzichè da un utente umano ( PROTOCOLLO HTTPS/HTTP )

I formati più comuni sono: 
- **XML** 
- **JSON** -> *JavaScript Object Notation*

>Es. chiamata: 
  https://maps.googleapis.com/maps/api/geocode/xml?address=strada%20spolverina%20mantova&key=......

L'URL è codificato in ASCII / UTF-8

In **JavaScript** è possibile effettuare chiamate a web service grazie ad **AJAX**:
- AJAX: *Asynchronous JavaScript And XML*
Per motivi di sicurezza l'oggetto <u>XMLHttpRequest</u> può effettuare richieste solo a server che si trovano sullo stesso dominio della pagina che contiene il codice JavaScript, questa viene chiamata **Same Origin Policy**.

## Motivi del successo
- Standard fissi
- Possono facilmente attraversare i firewall
- Praticamente ogni linguaggio di programmazione dispone di librerie per effettuare richieste HTTP
- Le richieste e le risposte utilizzano formati testuali
- Le richieste sono controllate
	- Operazioni **CRUD** = *Create, Read (o Retrieve), Update, Delete*
	- Non tutte le modifiche al db sono consentite, ma solo quelle previste dal WS

## REST *vs* SOAP
### Rest
> *Representational State Transfer (trasferimento di stato rappresentazionale)*

**REST è uno stile architetturale**, cioè un insieme di principi e vincoli da usare
nella progettazione di un servizio. REST non è quindi un linguaggio, ma solo un
insieme di "regole di progettazione".

Caratteristiche e info:
- I WS che rispettano i principi REST sono dette RESTFul.
- Può usare sicurezza a livello di trasporto come HTTPS, ma non ha standard di sicurezza integrati al livello di **SOAP**.
- E' generalmente considerato più semplice e flessibile. Gli sviluppatori possono facilmente lavorare con REST usando gli strumenti e le librerie disponibili per HTTP.

Caratteristiche delle richieste:
- Le richieste **GET devono essere SAFE** ( *cioè non devono mai modificare lo stato*
*delle risorse sul server* )
- Le richieste **DELETE devono sempre essere IDEMPOTENTI** ( *Il risultato di due o*
*più DELETE deve essere identico al risultato di una sola invocazione* )
- **Ogni richiesta deve essere STATELESS** ( *Ogni richiesta deve contenere tutte*
*le informazioni che servono al server per gestire la risposta stessa* ) 

### Soap
> *Simple Object Access Protocol*

**SOAP è un protocollo più formale** che definisce un messaggio **rigoroso e regole di scambio**, usando XML per il formato del messaggio. Può operare su diversi protocolli come HTTP, SMTP, TCP, e altri. Le specifiche di SOAP sono mantenute da **W3C**.

Caratteristiche principali:
- **Formato del Messaggio** 
	- SOAP utilizza **XML** per formattare i dati dei messaggi, garantendo così una trasmissione di dati precisa e rigorosamente tipizzata
- **Indipendenza dal Trasporto** 
	- Sebbene SOAP sia comunemente utilizzato su HTTP, supporta diversi altri protocolli di trasporto come **SMTP, TCP**.
- **Sicurezza** 
	- SOAP supporta standard di sicurezza come crittografia, autenticazione e integrità del messaggio.
	- Supporta WS-Security, che include specifiche per la sicurezza più robuste come integrità del messaggio e privacy, oltre a estensioni per transazioni, affidabilità dei messaggi e altro.
- **Transazionalità** 
	- Le estensioni di SOAP supportano la gestione delle transazioni, assicurando che le operazioni possano essere completate con successo o completamente annullate in caso di errore

> [!note] WSDL
> **WSDL ( *Simile a XSM* ) definisce un formato standard per descrivere in modo**
**formale le operazioni, i parametri e i formati di risposta di un**
**servizio web**. E’ comunemente usato in combinazione con SOAP per
fornire una descrizione dettagliata delle operazioni supportate dai
servizi web SOAP.
