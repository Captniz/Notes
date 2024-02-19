## **STP - VLAN**

- Switch
- Segmenti di LAN
- **Dominio di collisione**: Area di una rete in cui si possono verificare collisioni
- Percorsi fisici ridondanti per evitare guasti o blocchi
	- **Broadcast storm:** Molteplici frame di broadcast che occupano l'intera banda in una rete con percorsi fisici ridondanti.
	- Gestione dei collegamenti affidata al protocollo **STP ( Spanning Tree Protocol )
		- *Protocollo definito nello standard IEEE 802.1. Crea un albero gerarchico che mantiene i percorsi alternativi da usare in caso di necessita, quindi si lasciano loop fisici ma si eliminano a livello di topologia logica.**
		- Se in un certo istante un segmento della rete dovesse diventare irraggiungibile, STP riconfigurerà la topologia logica, ristabilendo il collegamento.
		- Ogni switch della LAN invia dei messaggi detti **BPDU (Bridge Protocol Data Unit)** trasmessi da tutte le porte per conoscere I'esistenza di altri switch. Le BPDU:
			- Calcolano il percorso più breve da ogni switch alla root.
			- Designano il **Root bridge**: *Switch centrale alla rete*.
			- Designano il **Designated switch** ( *Switch più vicino alla Root* ) per ogni LAN.
			- Designano la **Designated port**: porta attiva per l' STP.
			- Scelgono la **Root port**: *Porta con il miglior percorso verso la root*. Le porte possono avere questi stati:
				- **Blocking**: Accetta solo BPDU.
				- **Listening**: Sta costruendo la topologia “attiva” della rete.
				- **Learning**: Sta costruendo la tabella di bridging, quindi è in grado di apprendere gli indirizzi fisici, ma non invia né riceve dati.
				- **Forwarding**: Può inviare e ricevere dati.
				- **Disabled**: Disabilitata dall'amministratore.
		- **RSTP:** E' la nuova versione con tempo di convergenza minore di circa 6 secondi.
			- Aggiunge i percorsi ***alternate*** subito disponibili dopo che si riceve un timeout della connessione senza che sia necessario rimappare i percorsi.
			- Aggiunge le porte ***backup***, cioè porte presenti nello stesso segmento di quelle forwarding. 
- **Dominio di broadcast**: Insieme di computer che riceve un messaggio di broadcast trasmesso da uno di essi.

| HW     | Dom. Collisione | Dom. Broadcast |
| ------ | --------------- | -------------- |
| Hub    |       1 x ALL          |    1 x ALL            |
| Switch |          1 x 1       |         1 x ALL       |
| Router       |     1 x 1            |     1 x 1           |

- **VLAN**:  Sottoreti logiche attraverso gli switch. La rete rimane configurata con la stessa topologia fisica, mentre cambia la topologia logica. 
	- Quando un host su una VLAN deve comunicare con un host su un'altra VLAN, è necessaria la presenza di un router.
	- Se invece si usano switch con funzionalità di routing, detti **switch Layer-3** si toglie la necessita' del router.
	- Il frame Ethernet non prevede un campo per effettuare il tagging delle VLAN per questo si e' inventato lo standard **1EEE 802.1q.**
		-  4 Byte
		- **Tag Protocol ID (TPID)** ~ 2 byte ~ Identificativo del frame come un frame IEEE 802.1q.
		- **Tag Control Information (TCI)** ~ 2 byte
			- **User priority** ~ 3 bit ~  Livello di priorità del frame.
			- **Canonical Format Indicator** ~ 1 bit ~ Segnala i frame da scartare in caso di congestione in rete.
			- **VLAN ID** ~ 12 bit ~ indica a quale VLAN appartiene il frame.
	- I vantaggi sono:
		- Semplice aggiungere, cambiare o spostare gli host sulla rete.
		- Miglioramento delle prestazioni.
		- Migliora la sicurezza.
		- Riduce i costi relativi agli apparati di rete impiegati.

## **Firewall**

- Controllo del traffico di rete e blocco di alcuni pacchetti
	- **Application Level Firewall**: *Lavora a livello Application.* A questa categoria appartengono i ***proxy***. Valuta il contenuto applicativo dei pacchetti, riconoscendo e bloccando i dati appartenenti a virus e simili.
		- Il **Proxy** e' un programma che si interpone tra server e client.
			- **Connettività**: permettere a una intera rete privata di accedere a Internet attraverso un unico computer.
			- **Privacy**: mascherare il vero indirizzo IP del client in modo che il server non venga a conoscenza di chi ha effettuato la richiesta.
			- **Caching**: immagazzinare per un certo tempo i risultati delle richieste di un client nel caso un altro client effettui le stesse richieste.
			- **Monitoraggio**: tenere traccia di tutte le operazioni effettuate.
			- **Amministrazione**: applicare regole definite dall’ amministratore di sistema per determinare quali richieste inoltrare e quali rifiutare.
			- **Filtraggio**: svolgere funzioni di firewall a livello Application.
			- **Restrizioni**: creare una zona neutra non appartenente alla LAN.
		- Tipi di proxy:
			- **Single Proxy Topology**: Utilizza un singolo Proxy Server per servire l'intera rete.
			- **Multiple Proxy Vertical Topology**: Preferibile nel caso di reti medio-grandi, stabilendo un proxy primario a cui gli altri si connettono. I proxy secondari agiscono come client del primario.
			- **Multiple Proxy Horizontal Topology**: consente di bilanciare il carico tra i server in base alle richieste dei client.
	- **Packet Filter Firewall**: *Lavora a livello Network e a livello Transport.* Il Packet Filter Firewall è molto più veloce in quanto il controllo viene effettuato sui pochi byte di header. Controlla:
		- IP di origine/destinazione.
		- Numero della porta TCP/UDP di origine e destinazione.
		- Protocollo di livello superiore usato
	- **Stateful Packet Inspection Firewall**: *Agisce a livello Transport.* Permette, oltre al controllo dell' header del pacchetto dati, anche di analizzarne il contenuto. Salva i risultati su una tabella e li confronta con i prossimi pacchetti simili.
- **ACL (Access Control List ):** Sistema di configurazione del firewall.
	- Le ACL vengono elaborate dal router in maniera sequenziale ( A cascata ) in base all'ordine in cui sono state inserite le varie clausole.
		- Questo permette di decidere l'ordine di processazione/importanza dei pacchetti.
		- Se il pacchetto non soddisfa nessuna delle condizioni viene scartato.
		- **Standard ACL**: Specificano delle limitazioni ai pacchetti guardando esclusivamente l'indirizzo della sorgente.
		- **Extended ACL**: Pongono le limitazioni ai pacchetti in base a molte specifiche -> Protocollo usato, I'indirizzo di sorgente, l’indirizzo di destinazione . . .

## **NAT**

- **NAT**: Tecnica attuata dal router che, sostituisce l’indirizzo IP nell'intestazione di un pacchetto. 
	- Permette a una rete locale, che usa una classe di indirizzi privata, di accedere a Internet usando un solo indirizzo pubblico fornito dall'Internet Service Provider
	- NAT usa una tabella contenente la corrispondenza tra le socket interne ed esterne in uso. 
	- **PAT (Port Address Translation)** consente al router di utilizzare un singolo indirizzo IP per gestire oltre 64.000 connessioni private contemporaneamente. Questo significa che può traslare più indirizzi IP client per un medesimo indirizzo IP destinazione cambiando solo la porta.
- **DMZ (DeMilitarized Zone)**: Si tratta di un'area in cui sia il traffico WAN sia quello LAN sono fortemente limitati e controllati. Tale configurazione viene normalmente utilizzata per permettere ai server posizionati sulla DMZ di fornire servizi all'esterno senza compromettere la sicurezza della rete aziendale interna.