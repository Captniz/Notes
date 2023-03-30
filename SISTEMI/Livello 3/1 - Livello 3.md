#sistemi #livelloTre

PDF: \[ [[]] ]

---

## Utilizzo del Livello 3
Le reti a computazione di pacchetto si basano sul **protocollo IP**, posizionato sul livello 3.; il protocollo IP introduce anche il suo sistema di indirizzamento. 

Ci sono **due versioni** del protocollo IP:
- **IPV4**
	󰘍 **4 Byte** di dato per l'indirizzo.
- **IPV6**
	󰘍 **6 Byte** di dato per l'indirizzo (Meno utilizzato ma necessario a causa del fatto che l' IPV4 non fornisce abbastanza IP per tutti).


ES TEMP
Si vuole inviare un pacchetto di  9000 byte con protocollo IPV4.
La dimensione massima del payload è 3000 byte.

- Flag
- Identification (10:1234)
- Fragment offset
- Total length

| 3000  | 3000  | 3000  |
| ---- | ---- | ---- |
| 001  | 001  | 000  | 
| 1234 | 1234 | 1234 |
| 0    | 375  | 750  |
| 3020 | 3020 | 3020 |
