# **BIBLIOTECHE DI ROMA**
# **Stima degli sforzi**

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


##### Tabelle 2. Pesi per la classificazione dei Function Point
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


**Seguendo le tabelle 1 e 2, nel nostro caso avremo:**
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

<!-- TODO: aggiungere PL_5, Proroga Prenotazione 
-->
Considerando il mix tecnologico previsto per l’implementazione:

- **Backend** sviluppato in **Go**: 60% dell’implementazione, con un rapporto di circa **70 SLOC per FP**
- **Gestione dei dati** tramite **comandi SQL**: 15% del progetto, con un rapporto di circa **12 SLOC per FP**
- **Frontend** in **Vue.js**: 25% dell’implementazione, con una stima di **50 SLOC per FP**

Il valore medio calcolato è:

$$
SLOC/FP = 0.60 \cdot 70 + 0.15 \cdot 12 + 0.25 \cdot 50 = 56.3
$$

La dimensione complessiva del progetto, espressa in **KSLOC (Kilo Source Lines of Code)**, risulta quindi:

$$
SIZE = \frac{101 \times 56.3}{1000} = \boxed{5.689} \text{ KSLOC}
$$

## ***Il fattore E***
Il fattore $E$ si calcola tramite:
$$
E = B + 0.01 \cdot \sum_{j=1}^{5} SF_j
$$

e rappresenta l’esponente nella formula di calcolo dello sforzo del modello COCOMO II. Viene calcolato in base a 5 **fattori di scala (Scale Factors)**:

1. **PREC** – Precedenti esperienze con progetti simili
2. **FLEX** – Flessibilità dei requisiti
3. **RESL** – Risolutezza dell’architettura e dei rischi
4. **TEAM** – Capacità e coesione del team
5. **PMAT** – Maturità dei processi

A ciascun fattore viene assegnato un valore da 0 a 5, dove 0 rappresenta una condizione ottimale (molto alta) e 5 una condizione critica (molto bassa). Nel contesto di questo progetto, sono stati assegnati i seguenti valori:

| Fattore | Valore assegnato | Descrizione |
|--------|------------------|-------------|
| PREC   | 4                | In gran parte familiare |
| FLEX   | 3                | Qualche flessibilità nei requisiti |
| RESL   | 3                | Architettura definita al 60% |
| TEAM   | 0                | Interazione continua nel team |
| PMAT   | 5                | Maturità di processo molto alta (SW-CMM livello 5) |

La somma dei fattori scala è quindi:

$$
\sum SF_j = 4 + 3 + 3 + 0 + 5 = \boxed{15}
$$

Applicando la formula:

$$
E = 1.01 + 0.01 \cdot \sum SF_j = 1.01 + 0.01 \cdot 15 = \boxed{1.16}
$$

## ***Fattore EM***
Il valore $\prod{EM_i}$ rappresenta il prodotto dei fattori di costo (Effort Multipliers) nel modello COCOMO II, che influenzano lo sforzo di sviluppo in funzione delle caratteristiche del progetto, del team e del contesto tecnologico.

In questo progetto sono stati considerati i 7 fattori di costo riportati nella seguente tabella, ciascuno valutato secondo il proprio impatto stimato sul progetto:

| Fattore | Significato                                 | Livello scelto | Valore EM |
|--------|----------------------------------------------|----------------|------------|
| **PERS** | Capacità del personale                     | Alto           | 0.83       |
| **RCPX** | Complessità del prodotto                   | Alto           | 1.33       |
| **PDIF** | Diversità della piattaforma                | Basso          | 0.87       |
| **PREX** | Esperienza precedente del team             | Alto           | 0.87       |
| **FCIL** | Vincoli hardware                           | Nominale       | 1.00       |
| **RUSE** | Riutilizzabilità del codice                | Nominale       | 1.00       |
| **SCED** | Vincoli temporali                          | Nominale       | 1.00       |

Il valore complessivo del fattore $\prod$ EM_i è calcolato come il prodotto dei singoli coefficienti:

$$
\prod EM_i = 0.83 \cdot 1.33 \cdot 0.87 \cdot 0.87 \cdot 1.00 \cdot 1.00 \cdot 1.00 = \boxed{0.836}
$$

### ***Calcolo dello sforzo (PM)***
$$
PM = 2.94 \cdot (5.689)^{1.16} \cdot 0.836 = \boxed{18.47} \text{ persone-mese}
$$

### ***Calcolo della durata (TDEV)***

La durata del progetto viene stimata con la formula:

$$
TDEV = 3 \cdot PM \cdot (0.33 + 0.2 \cdot (E - 1.01))
$$

Sostituendo i valori:

- **PM = 18.47**
- **E = 1.16**

Si ottiene:

$$
TDEV = 3 \cdot 18.47 \cdot (0.33 + 0.2 \cdot (1.16 - 1.01)) = \boxed{19.94} \text{ mesi}
$$

### ***Ripartizione stimata dei costi dell'architettura fisica***

| Voce di costo                                   | Quantità | Costo unitario (€) | Totale (€) |
|------------------------------------------------|----------|---------------------|------------|
| Server cloud								     | 12 mesi  | 1.000               | 12.000     |
| Licenze software 							     | 1        | 3.000               | 3.000      |
| Backup e storage cloud                         | 12 mesi  | 200                 | 2.400      |
| Postazioni di lavoro                           | 180      | 1.000               | 180.000    |
| Costi vari (rete, sicurezza, firewall, VPN...) | –        | –                   | 2000       |
| **Totale stimato**                             |          |                     | **€ 198.000** |

### ***Analisi preliminare dei costi***

Assumendo che:

- lo stipendio medio di un ingegnere del software varia dai 2.000 ai 4.000 euro al mese, si ipotizza uno stipendio medio di **3.000 euro**;
- i costi di overhead del team (viaggio, ufficio, mensa, strumenti) sono stimati nel **doppio del salario medio**, ovvero **6.000 euro al mese**;
- i costi dell’architettura fisica, comprensivi di licenze software, server cloud e strumenti di supporto, ammontano a **199.400 euro**;

il costo totale si ipotizza pari a:

$$
(18{,}47 \cdot 3.000\,€) + (6.000\,€ \cdot 19{,}94) + 199.400\,€ = \boxed{374.450\,€}
$$



## Revisioni
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|03/04/2025|Prima stesura del documento
|1.1|11/04/2025|Seconda stesura del documento