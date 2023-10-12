---
tags:
  - informatica
---
## **Definizione**
> <mark style="background: #8DA101AA;">**Insieme di file memorizzati permanentemente su una memoria ausiliaria, legati da relazioni. Interfacciazione della realtà attraverso il dato.**</mark>  

```ad-info
title: Relazioni
collapse: closed
Associazione di un dato dell'insieme `A` a un sottoinsieme di dati di `B` 
```
## **Database Management System (DBMS)**
### **Esempi**
- MySQL 
- PostgreSQL
### **Scopo**
> <mark style="background: #8DA101AA;">**Permette la creazione, popolazione, manipolazione e integrità del database.**</mark>

Questi scopi vengono raggiunti attraverso due tipi di linguaggio:
- ***DDL* ( Data Definition Language):**
	- Permette la creazione di tabelle, campi, database, constraints, etc...
- ***DML* ( Data Manipulation Language):** 
	- Permette la manipolazione, inserimento di dati di tutto ciò che riguarda un database

### **Caratteristiche**
#### **Indipendenza dei dati** 
> <mark style="background: #3A94C5AA;">**Per agire sui dati non devo sapere come i dati sono memorizzati fisicamente 
> ( astrazione )**</mark>

- ***Indipendenza fisica dei dati:***
	- La memorizzazione fisica non deve alterare in alcun modo le relazioni dal punto di vista logico.
-  ***Indipendenza fisica dei logica:***
	- Modificando lo schema logico ( relazioni e corrispondenze ) non si vanno a modificare le viste.

#### **Sicurezza**
> <mark style="background: #3A94C5AA;">**Le viste del database sono diverse, basate sull'utente**</mark>

#### **Vincoli di integrità**
> ...