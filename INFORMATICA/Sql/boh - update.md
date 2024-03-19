- Metti sempre l entità meno duratura ( anche a livello di tempo ) dentro a quella piu duratura, es. preside - scuola, per evitare di cancellare l'entità maggiore nel caso quella minore cambi

## Forme normali

### 1NF
> Tutti gli attributi devono essere atomici:
> - Non Strutturati
> - Non multi-valore


### 2NF
> E' in 1NF e non ha dipendenze di forma parziale, cioè quando un attributo non primo dipende parzialmente da una chiave. Esempio:
> - tab( <u>A, B</u>, C, D ) in cui C dipende solo da B
> - Diventa -> tab1( <u>A, B</u>, D ) / tab2( <u>B</u>, C )


### 3NF
> 