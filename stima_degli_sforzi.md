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

Il fattore **Size** , all'inizio del progetto, si può stimare a partire dai **Function Points (FP)**. Questa stima si basa sull'identificazione e sulla quantificazione di **cinque tipi principali**:
##### Tabella 1. Tipi di Function Point
| Tipo di Function Point | Descrizione | Peso Low | Peso Avg | Peso High |
|------------------------|-------------|----------|----------|-----------|
| **External Input (EI)** | Conta ogni tipo unico di input di dati o comandi fornito dall’utente che entra nei confini esterni del sistema software. | 3 | 4 | 6 |
| **External Output (EO)** | Conta ogni tipo unico di output di dati o comandi che lascia i confini esterni del sistema software. | 4 | 5 | 7 |
| **Internal Logical File (ILF)** | Conta ogni gruppo logico principale di dati o informazioni di controllo utente che il sistema genera, utilizza o mantiene internamente come file logico. | 7 | 10 | 15 |
| **External Interface File (EIF)** | File condivisi tra sistemi software che vengono utilizzati dal sistema, ma gestiti da un altro sistema. | 5 | 7 | 10 |
| **External Inquiry (EQ)** | Conta ogni combinazione unica input-output in cui un input genera immediatamente un output, senza elaborazioni complesse. | 3 | 4 | 6 |


##### Tabella 2. Pesi per la classificazione dei Function Point
###### Per ILF (Internal Logical Files) e EIF (External Interface Files)

| Elementi Record (RET) | Elementi Dati (DET)        | 1–19 | 20–50 | 51+  |
|------------------------|-----------------------------|------|--------|------|
| 1                      |                             | Low  | Low    | Avg  |
| 2–5                    |                             | Low  | Avg    | High |
| 6+                     |                             | Avg  | High   | High |

###### Per EO (External Output) e EQ (External Inquiry)

| Tipi di File (FTR)     | Elementi Dati (DET)        | 1–5  | 6–19   | 20+  |
|------------------------|-----------------------------|------|--------|------|
| 0–1                    |                             | Low  | Low    | Avg  |
| 2–3                    |                             | Low  | Avg    | High |
| 4+                     |                             | Avg  | High   | High |

###### Per EI (External Input)

| Tipi di File (FTR)     | Elementi Dati (DET)        | 1–4  | 5–15   | 16+  |
|------------------------|-----------------------------|------|--------|------|
| 0–1                    |                             | Low  | Low    | Avg  |
| 2–3                    |                             | Low  | Avg    | High |
| 4+                     |                             | Avg  | High   | High |


Seguendo la tabella 1 e 2, nel nostro caso avremo:
#### Stima dei Function Point (UFP)

##### Function Point per singola funzione

| ID     | Nome                                           | Tipo | Complessità | Peso UFP |
|--------|------------------------------------------------|------|-------------|----------|
| AU_1   | Autenticazione sistema interno                 | EI   | Low         | 3        |
| AU_2   | Autenticazione tramite SPID                    | EI   | Avg         | 4        |
| AU_3   | Modifica password                              | EI   | Low         | 3        |
| AU_4   | Registrazione                                   | EI   | Low         | 3        |
| AU_5   | Logout                                          | EI   | Low         | 3        |
| T_1    | Nuovo tesseramento                             | EI   | Avg         | 4        |
| T_2    | Rinnovo tesseramento                           | EI   | Avg         | 4        |
| T_3    | Cancellazione tesseramento                     | EI   | Avg         | 4        |
| T_4    | Smarrimento tessera                            | EI   | Avg         | 4        |
| T_5    | Furto tessera                                   | EI   | Avg         | 4        |
| G_1    | Partecipazione gamification                    | EI   | Avg         | 4        |
| G_2    | Gestione profilo                               | EI   | Avg         | 4        |
| G_3    | Inserimento commento                           | EI   | Avg         | 4        |
| G_4    | Segnalazione commento                          | EI   | Avg         | 4        |
| G_5    | Riscatto punti                                 | EI   | Avg         | 4        |
| PL_1   | Ricerca e richiesta libro                      | EQ   | Avg         | 4        |
| PL_2   | Restituzione prestito                          | EI   | Low         | 3        |
| PL_3   | Estensione prestito                            | EI   | Avg         | 4        |
| PL_4   | Richiesta e-book                               | EI   | Avg         | 4        |
| PS_1   | Prenotazione spazio                            | EI   | Avg         | 4        |
| PS_2   | Allungamento prenotazione                      | EI   | Avg         | 4        |
| PS_3   | Cancellazione richiesta                        | EQ   | Low         | 3        |
| PS_4   | Segnalazione comportamento                     | EQ   | Low         | 3        |
| SA_1   | Caricamento libri                              | EI   | Avg         | 4        |
| SA_2   | Segnalazione prestito dal vivo                 | EI   | Avg         | 4        |
| SA_3   | Segnalazione notizie                           | EI   | Avg         | 4        |
| SA_4   | Gestione pagina biblioteca                     | EI   | Avg         | 4        |
|        | **Totale**                                     |      |             | **101 UFP** |

Considerando il mix tecnologico previsto per l’implementazione:

- 40% Python (50 SLOC per FP)
- 30% C++ (80 SLOC per FP)
- 25% JavaScript (50 SLOC per FP)
- 5% Java (80 SLOC per FP)

Il valore medio risultante è pari a **60,5 SLOC per FP**.

La dimensione finale del software, espressa in **KSLOC (Kilo Source Lines of Code)**, è quindi:

$$
SIZE = \frac{101 \times 60.5}{1000} = 6.111 \text{ KSLOC}
$$




<!--
Il fattore $E$ si calcola tramite:
$$
E = B + 0.01 \cdot \sum_{j=1}^{5} SF_j
$$
-->



## Revisioni
||||
|--|--|--|
|Numero|Data|Descrizione|
|1.1|03/04/2025|Prima stesura del documento