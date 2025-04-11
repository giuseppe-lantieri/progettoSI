# **BIBLIOTECHE DI ROMA**
# **Stima degli sforzi**

<!--
Stima degli Sforzi (solo se non avete usato COCOMO II in precedenza): si fa la stima degli sforzi tramite il modello dei Function Points, questo sistema si basa sul documento Modello dei Casi d'uso.
-->
## ***Introduzione***
Il seguente documento ha lo scopo di stimare gli sforzi per la realizzazione del servizio proposto attraverso il modello **COCOMO II** (Constructive Cost Model). COCOMO II si distingue per la sua capacità di modellare processi non sequenziali e sviluppi rapidi; di fornire gli strumenti adeguati per la stima in progetti basati sul riutilizzo del software; per la considerazione degli effetti della maturità del processo di sviluppo. Infatti team con un alto grado di organizzazione e processi ben definiti possono ottenere stime più affidabili e costi più contenuti.
Grazie a queste caratteristiche, COCOMO II si conferma uno strumento solido e adattabile per la stima degli sforzi nei progetti software complessi, eterogenei e in continua evoluzione.

## ***Stima degli sforzi con COCOMO II***
In COCOMO II gli sforzi sono espressi come **"Person-Months" (PM)**, ovvero il numero di "Persone-Mesi" necessari per completare il progetto. Un person-month corrisponde a 152 ore di lavoro.
Il calcolo dello sforzo si basa sulla seguente formula:
$$
PM = A \times \text{Size}^{E} \times \prod_{i=1}^{n} \text{EM}_i
$$
Dove:
- **A** è una costante che rappresenta una stima della produttività media, espressa in Person-months per KSLOC. In questo caso, seguendo lo standard di COCOMO II.2000, vale 2.94.
- **Size** è la dimensione stimata del software, espressa in KLOCK (Kilo Source Lines of Code), ovvero migliaia di righe di codice;
- **E** è un esponente che riflette la scala del progetto;
- **EM<sub>i</sub>** sono i moltiplicatori di sforzo (Effort Multipliers), ciascuno dei quali rappresenta un diverso aspetto che può influenzare l'impegno richiesto (ad esempio: esperienza del personale, complessità del prodotto, uso di strumenti, vincoli di tempo, ecc.).

## ***Il parametro SIZE***
L'input più significativo è **Size**. Esso non è un parametro quantitativo, ma viene associato a un **fattore esponenziale** *E* che amplifica o riduce l'impatto della dimensione stessa sullo sforzo complessivo.

Il fattore **Size** si può stimare a partire dai **Function Points (FP)**, 

Il fattore $E$ si calcola tramite:
$$
E = B + 0.01 \cdot \sum_{j=1}^{5} SF_j
$$




## Revisioni
||||
|--|--|--|
|Numero|Data|Descrizione|
|1.1|03/04/2025|Prima stesura del documento