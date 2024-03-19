---
tags:
  - informatica
---
## Vincoli intra-relazionali

```SQL
CREATE TABLE x (
a int NOT NULL,   --Impone un valore nel campo
b int UNIQUE,     --Impone che non ci siano due valori uguali nella colonna
c int PRIMARY KEY,-- Un attributo che identifica univocamente un record
d int DEFAULT 0   -- Si imposta un default per il campo
)
``` 
Altro esempio di unique:
```SQL
CREATE TABLE x (
nome varchar(20) NOT NULL,   
cognome varchar(20) NOT NULL,
nickname varchar(20) NOT NULL UNIQUE --L'attr nickname è unico

UNIQUE(nome,cognome) --Gli attr nome e cognome sono unici come tupla, si può avere lo stesso nome o lo stesso cognome ma non entrambi
)
```

## Vincoli inter-relazionali

- Vincoli di integrità referenziale
- Foreign key
	```SQL
	CREATE TABLE x (
	a serial,
	b int REFERENCES tabellay(colonnax), --Un solo attr
	c int FOREIGN KEY ???--Usato per due o più attributi
	)
	``` 
