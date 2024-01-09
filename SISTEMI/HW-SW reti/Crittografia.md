---
tags:
  - sistemi
---
## **Funzioni di hashing**

> Sono algoritmi che prendendo una **stringa** in input ne ricavano **un codice univoco e di lunghezza fissa da cui non è possibile risalire alla string originale**

> [!warning]-
> In realtà l'**hash** non è strettamente univoco dato che avendo 16 bit di informazioni le possibilità di output sono finite mentre le stringhe in input non hanno questa limitazione; perciò si può incorrere nel caso due stringhe diano lo stesso output

Questa operazione ( *Detta **digest*** ) è possibile attraverso una moltitudine di operazioni matematiche unilaterali ( *Es: addizioni* )

###### **Funzioni più famose:**
- **MD5**
- **SHA256**
- **SHA512**