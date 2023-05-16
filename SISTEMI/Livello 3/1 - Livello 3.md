#sistemi #livelloTre

PDFs:
\[ [[06 - LVL3.pdf]]]
\[[[07 - ARP.pdf]]]

---
## Il protocollo IP ( Internet Protocol )
Il protocollo IP ha il suo proprio sistema di indirizzamento ed è indipendente dal livello 1 e 2.

**Ci sono due tipi di IP:**

| IPV4                      | IPV6                                                 |
| ------------------------- | ---------------------------------------------------- |
| IP attualmente utilizzato | Futuro sostituto dell IPV4 grazie alla sua lunghezza |

### IPV4

**Caratteristiche dell' IPV4**
- Non confermato
- Incapsulamento
- Frammentazione
- *NO* Controllo di flusso
- *NO* Consegna in sequenza
- *NO* Controllo errori
- Connection-less

Prevede **4 byte** per indirizzo che può essere di tre tipologie:
- **Unicast:** Un solo destinatario
- **Multicast:** Un gruppo di destinatari
- **Broadcast:** Tutti i destinatari

Un IP è diviso in due parti **<mark style="background: #F57D26AA;">Network address</mark> e <mark style="background: #8DA101AA;">Host address</mark>**; entrambe sono variabili. Per determinarne la lunghezza si usa la **Subnet mask**.

| Tipo di IP | Byte Network Address | Byte Host Address | Subnet Mask   |
| ---------- | -------------------- | ----------------- | ------------- |
| A          | 1                    | 3                 | 255.0.0.0     |
| B          | 2                    | 2                 | 255.255.0.0   |
| C          | 3                    | 1                 | 255.255.255.0 |

La **Subnet Mask** rappresenta con numeri decimali i byte, tutti i numeri a uno sono utilizzati dal Network Address.

>**Es.** 
>IP di tipo C
>
> IP:            192.168.0.0  -> xxxxxxxx.xxxxxxxx.xxxxxxxx.( Host address )
> SUBNET: 255.255.0.0 -> 11111111.11111111.11111111.00000000

> [!warning]- Tabelle di routing
> Schemi che dicono al router dove inviare un pacchetto rispetto all'IP del destinatario del pacchetto.
>
> Associano una **rete di destinazione e la sua maschera al prossimo router** a cui inviare il pacchetto per raggiungere la destinazione.

