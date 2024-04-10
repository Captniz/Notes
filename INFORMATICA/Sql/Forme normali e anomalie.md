- Metti sempre l entità meno duratura ( anche a livello di tempo ) dentro a quella piu duratura, es. preside - scuola, per evitare di cancellare l'entità maggiore nel caso quella minore cambi

## Forme normali

> [!info]- Dipendenza funzionale
> Si dice che X determina funzionalmente Y se non esistono due tuple con valori identici in X e Y.
> 
> Tutti gli attributi non primi ( *Che non appartengono alla chiave primaria* ) dipendono funzionalmente dalla chiave.

### 1NF
> Tutti gli attributi devono essere atomici:
> - Non Strutturati
> - Non multi-valore


### 2NF
> E' in 1NF e non ha dipendenze di forma parziale, cioè quando un attributo non primo dipende parzialmente da una chiave. Esempio:
> - tab( <u>A, B</u>, C, D ) in cui C dipende solo da B
> - Diventa -> tab1( <u>A, B</u>, D ) / tab2( <u>B</u>, C )


### 3NF
> Elimina dipendenze di tipo transitivo
> Come la 2NF ma gli attributi non sono primary key
> Es. ( <u>A</u>,B,C ) in cui B dipende da A ma C dipende solo da B, quindi *dipende da A transitando attraverso C*


## Anomalie da inserimento e modifica
> Errori nei dati del DB corrette dalle forme normali

Es. 
- Quando aggiungi una foreign key che non esiste nella sua tabella 
- Cambio di primary key che sono in una reference di foreign key
- Errori grammaticali negli inserimenti
- Ridondanze