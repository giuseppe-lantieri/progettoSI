# BIBLIOTECHE DI ROMA - Documento di Visione

## Introduzione
Il Comune di Roma prevede di realizzare un nuovo portale online per la gestione del sistema bibliotecario, che consenta agli utenti un accesso semplice e digitale ai servizi offerti. L’obiettivo principale consiste nell’offrire un’interfaccia intuitiva per usufruire dei seguenti servizi:

- **Prenotazione Libri**
- **Prestito Libri (fisico e ebook)**
- **Prenotazione Posto** (ove disponibile)
- **Servizio Wi-Fi**
- **Servizio Tesseramento**

Il portale includerà inoltre una sezione riservata al personale autorizzato, che consentirà di:
- Gestire i libri presenti
- Segnalare eventuali criticità negli spazi comuni
- Amministrare il profilo della biblioteca

Sono previste, inoltre, le seguenti funzionalità:
- Integrazione dell’autenticazione tramite i servizi di Stato
- Aggregazione dei database
- Funzionalità di gamification

## Prenotazione Libri
Il portale consentirà agli utenti, autenticati o meno, di verificare la disponibilità dei libri, distinguendo tra copie fisiche ed ebook.  
- **Libri Fisici:** Verranno fornite informazioni relative alla biblioteca che detiene il libro, alla sua ubicazione e alla prima disponibilità. Qualora il libro risulti attualmente in prestito, l’utente potrà richiedere l’estensione del periodo di prestito, salvo l’esistenza di prenotazioni in corso.
- **Ebook:** Verranno mostrate le specifiche relative al formato digitale, conformemente alle regole d’uso definite dalla singola biblioteca.

## Prestito Libri
Le modalità di prestito variano in base al formato del libro.

### Fisico
Poiché il libro fisico non può essere consegnato direttamente online, il portale dovrà eseguire le seguenti operazioni:
1. Segnalare l’indisponibilità del libro per un periodo di 14 giorni.
2. Generare una ricevuta da inviare all’utente, da presentare al momento del ritiro.
3. Consentire al bibliotecario di verificare l’autenticità della ricevuta.
4. Impedire ulteriori prenotazioni sul libro fino alla scadenza della prenotazione in corso.
5. Consentire all’utente che ha prenotato di estendere il periodo di prestito qualora non vi siano altre prenotazioni pendenti.

### Ebook
Il periodo di prestito per gli ebook sarà definito in base alla licenza e ai termini di utilizzo stabiliti tra la biblioteca e il fornitore. Tra gli scenari possibili si prevedono:
1. **Licenza di libera distribuzione e fruizione:** L’ebook verrà fornito all’utente in copia digitale, corredato da una firma digitale che ne certifichi l’autenticità, senza includere il diritto alla ridistribuzione.
2. **Licenza di sola lettura:** L’ebook sarà consultabile esclusivamente in modalità “sola lettura” all’interno della sezione dedicata del profilo utente per un periodo limitato a 14 giorni, mediante l’utilizzo di tecnologie idonee a garantire il rispetto dei requisiti di sicurezza.

## Prenotazione Posto
Per le biblioteche che mettono a disposizione spazi di studio, quali tavoli e sale per il co-working, il portale dovrà:
1. Verificare la disponibilità del posto e segnalarlo per la biblioteca selezionata.
2. Gestire le prenotazioni in condizioni di elevata richiesta.
3. Consentire il controllo dello stato della prenotazione da parte di un bibliotecario.
4. Inviare una notifica al bibliotecario al termine della prenotazione, per permettere il relativo controllo.
5. Consentire all’utente di prolungare la prenotazione, in base alla disponibilità.

## Servizio di Tesseramento
Il portale offrirà differenti servizi di tesseramento, alcuni a pagamento e altri gratuiti. La tessera d’iscrizione, di natura personale, avrà una validità prestabilita. I bibliotecari saranno abilitati a:
- Emettere nuove tessere per gli utenti.
- Proporre l’introduzione di nuove tipologie di tessera.
- Richiedere l’annullamento di tessere esistenti.

## Notizie
Il portale comprenderà una sezione riservata alle notizie, che sarà presentata sia in forma aggregata nella pagina principale sia in dettaglio nelle pagine dedicate a ciascuna biblioteca.

## Posizione
Il portale metterà a disposizione una mappa interattiva delle biblioteche, fornendo informazioni dettagliate sulla loro ubicazione e indicazioni stradali. L’utente potrà interagire con la mappa per individuare la biblioteca più vicina al proprio municipio, senza però avere la possibilità di modificarla.

## Database Unificati
Il portale consentirà l’interrogazione dei database delle varie biblioteche attraverso un unico punto d’accesso, garantendo la condivisione e l’accessibilità di tutte le informazioni. I database esistenti saranno integrati in un sistema centralizzato, migliorando la gestione dei dati grazie all’adozione di soluzioni moderne, backup frequenti e politiche di distribuzione conformi alle linee guida del progetto OPEN DATA.

## Integrazione dei Servizi di Login di Stato
Il portale integrerà i servizi di autenticazione offerti dallo Stato italiano (ad esempio, SPID e CIE), assicurando un login rapido e sicuro, requisito fondamentale per le applicazioni statali.

## Gamification
Il portale comprenderà meccanismi di gamification finalizzati a incentivare l’interazione degli utenti. Verranno assegnati punti per diverse attività, quali:
- Inserimento di informazioni relative ai libri.
- Pubblicazione di recensioni.
- Gestione dei prestiti.
- Altre interazioni all’interno della piattaforma.

Il sistema prevede inoltre la penalizzazione di comportamenti negativi, tra cui:
- Recensioni considerate inopportune dai bibliotecari.
- Smarrimento di un libro.
- Ritardi nella riconsegna.
- Restituzione di un libro in condizioni non ottimali (danni o usura).

I punti accumulati potranno essere riscattati per l’ottenimento di premi. Ad esempio:

| Azione                                       | Punteggio |
|----------------------------------------------|-----------|
| Commento ritenuto utile                      | +300      |
| Commento ritenuto inopportuno dai bibliotecari | -1.000    |

Le sezioni dedicate alla gamification saranno ottimizzate per un’ottimale visualizzazione e interazione anche su dispositivi mobili.

## Revisioni
| Versione | Data       | Descrizione                    |
|----------|------------|--------------------------------|
| 1.0      | 15/03/2025 | Prima stesura del documento    |
| 1.1      | 19/03/2025 | Seconda stesura del documento  |
| 1.2      | 25/03/2025 | Terza stesura del documento    |
| 1.3      | 09/04/2025 | Quarta stesura del documento   |
