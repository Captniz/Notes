---
tags:
  - sistemi
Date created: 2024-02-19T10:20:00
Related PDFs:
  - "[[01 - Crypto.pdf]]"
  - "[[02 - Diffie Hellman.pdf]]"
  - "[[03 - Public key encryption.pdf]]"
Related pages:
---
## Criptazione
### **Funzioni di hashing**

> Sono algoritmi che prendendo una **stringa** in input ne ricavano **un codice univoco e di lunghezza fissa da cui non è possibile risalire alla string originale**.
> Cambiando anche un **singolo bit** l'output **cambia di circa il 50%**.

> [!warning]-
> In realtà l'**hash** non è strettamente univoco dato che avendo 16 bit di informazioni le possibilità di output sono finite mentre le stringhe in input non hanno questa limitazione; perciò si può incorrere nel caso due stringhe diano lo stesso output

Questa operazione ( *Detta **digest*** ) è possibile attraverso una moltitudine di operazioni matematiche unilaterali ( *Es: addizioni* )

###### **Funzioni più famose:**
- **MD5**
- **SHA256**
- **SHA512**

### **Cifratura XOR**
> Un altro modo per vedere lo **XOR** e' come invertitore programmabile, dove il primo bit decide se invertire il secondo

**Proprietà dello XOR:**
- ( a :TiLogicXor: b ) :TiLogicXor: c = a :TiLogicXor: ( b  :TiLogicXor: c )
-  a :TiLogicXor: b = b :TiLogicXor: a
- a :TiLogicXor: a = 0
- a :TiLogicXor: 0 = a

### One time pad
> Schema crittografico basato sullo XOR. Specificatamente su una singola serie di bit casuali da utilizzare una singola volta.

A discapito della sua semplicità questo sistema offre il **più alto grado di sicurezza**, cioè nel caso in cui un hacker ottenga il testo cifrato, **quest' ultimo acquisisce 0 informazioni sulla chiave**. Questo e' detto **Perfect Security**.

> [!warning]-
> L'unica falla di questo sistema al momento, **e' che i bit generati non sono veramente casuali**, dando all' hacker la possibilità di trovare informazioni sulla chiave.
>
> Inoltre e' difficile da mettere in pratica per questi motivi:
> - La chiave deve essere casuale e condivisa tra le due parti comunicanti
> - La chiave deve essere lunga quanto il messaggio
> - La generazione di numeri casuali e' difficile e costosa

<br>

## Comunicazioni private
### Diffie Hellman
> Algoritmo di comunicazione privata in rete per lo scambio di una chiave di criptazione.
> Questo sistema previene attacchi **Man In the Middle**.

#### Esempio
> [!info]-
> Presupponiamo:
> - **A** -> Ente comunicante 1
> - **B** -> Ente comunicante 2
> - **C** -> Man In the Middle
##### 1
> **A e B** scelgono un *numero primo* e un *generatore*

- A : {17,3}
- B : {17,3}
- C : {17,3}

##### 2
> **A** genera un numero casuale e lo tiene per se

- A : {17,3,15}
- B : {17,3}
- C : {17,3}

##### 3
> **A** esegue il calcolo ($generatore^{nScelto} \; \% \; nPrimo$) e manda il risultato a **B**

$$3^{15} \; \% \; 17 = 6$$

- A : {17,3,15,6}
- B : {17,3,6}
- C : {17,3,6}

##### 4
> **B** ripete le operazioni *2* e *3* per se

$$nScelto = 13$$

$$3^{13} \; \% \; 17 = 12$$

- A : {17,3,15,6,12}
- B : {17,3,6,13,12}
- C : {17,3,6,12}

##### 5
> **A e B** ora eseguono il calcolo $nRicevuto^{nScelto} \; \% \; nPrimo$ ottenendo la chiave finale

$$A = 12^{15} \; \% \; 17 = 10$$
$$B = 6^{13} \; \% \; 17 = 10$$
- A : {17,3,15,6,12,**10**}
- B : {17,3,6,13,12,**10**}
- C : {17,3,6,12}

### Cifratura con chiave pubblica
> Algoritmo attuale per la comunicazione sicura e privata in rete

Questo algoritmo e' composto da una **chiave privata di decriptazione** e una **pubblica di criptazione**.  In questo modo anche se un messaggio criptato e' in chiaro a chiunque la chiave per **decriptarla e' privata per il destinatario**.

L'algoritmo e' nominato **RSA** ed e' stato creato *nel 1970 da tre ricercatori del MIT* 

L'algoritmo contrario **DSA** e' usato per fare una *Firma*, cioè una conferma della provenienza del messaggio: se **A** cripta con la sua chiave privata il messaggio e **B** riesce a decriptarla con la chiave pubblica di **A** allora può essere sicuro della provenienza del messaggio.