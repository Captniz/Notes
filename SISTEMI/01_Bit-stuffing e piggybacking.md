#sistemi #protocolli 

PDF: [ [[8 - Bit-stuffing and piggybacking.pdf]] ]

---

## Bit stuffing
#### Bit stuffing nel protocollo SDLC

> [!warning]- Protocollo SDLC
> Nel protocollo **SDLC** si usa un bit separatore, <mark style="background: #F85552AA;">0x7E</mark> (**`0111 1110`**), per distinguere tra *header* e *payload*.
In questo protocollo è presente oltre all *header* un *tail* che viene anch'esso separato con un bit separatore.

Il **Bit stuffing** è una tecnica che prevede di inserire uno **`0`** dopo cinque **`1`** consecutivi nella **PDU**.

Nel caso che del protocollo **SDLC** si usa il **Bit stuffing** per permettere alla **PDU** di contenere il bit separatore senza che venga riconosciuto.

ES:
>**PDU:**
`SEP 011111101110 SEP` -> `SEP 011111`**`0`**`101110 SEP` 

## Piggybacking
Il **PiggyBacking** è la tecnica di unire **ACK** e **PDU** in un unico pacchetto.