---
tags:
  - sistemi
Date created: 2024-02-19T10:24:00
Related PDFs: 
Related pages:
---
## Definizione

**Microcontrollori** -> Circuiti integrati / Microchip
- Linguaggio `C` 
- *Usati in:* Elettrodomestici, Auto
- Basso costo
- Piccoli 

**CPU** 
- *RISC* -> Reduced Instruction Set Computer
	- ARM / AVR
- *CISC* -> Complex Instruction Set Computer
	- INTEL / AMD

## Usi
### Comunicazione con micro :LiCpu:
Uno dei task più frequenti è quello di comunicare con altre periferiche, come:
- *Attuatori* : Grandezza elettrica -> Grandezza fisica
- *Sensori* : Grandezza fisica -> Grandezza elettrica

##### Metodi di lettura
- **GPIO** ( *General Purpose Input Output* ) : Possibilità di dare o togliere tensione ( *0V || 5V* ) e di impostare i pin su *lettura* o *scrittura* 
- **Pin analogici** : Pin con la possibilità di leggere una tensione *compresa* tra 0 e 5V attraverso un **ADC** ( *Analog to Digital Converter* ), che trasforma un segnale analogico in entrata in binario. Può anche avvenire la scrittura attraverso un **DAC**, contrario al **ADC**, o con un pin **PWM** ( *Pulse WIdth Modulation* ) che modula l'onda elettrica.
- **Bus** : 
	- **Seriale** :  *tx -> rx*
	- **I2C**
	- **SPI**