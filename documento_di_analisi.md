# Documento di Analisi – Gestione Biblioteche Romane

## 1. Introduzione
Nel documento inizieremo con una descrizione del sistema per poi continuare con l'analisi dei casi d’uso e del glossario per estrarre le classi di analisi descritte dalle schede CRC. Visualizzeremo le relazioni mediante diagrammi EBC e infine saranno presenti i diagrammi di sequenza

## 2. Visione di Sistema

Il portale dovrà fungere da sistema in grado di garantire la comunicazione  tra diversi attori:
- **UtenteGuest** e **Utente**: utenti finali che interagiscono con il sistema per cercare libri, effettuare prestiti, prenotare spazi e partecipare alle attività di gamification.
- **Bibliotecario**: operatore con privilegi amministrativi, responsabile della gestione dei libri, del monitoraggio dei prestiti, e della pubblicazione di notizie.
- **Servizio Esterno**: integrazione con sistemi di autenticazione esterni (es. CIE, SPID) per agevolare l’accesso al portale.

La piattaforma garantisce una gestione centralizzata e sicura delle operazioni, per assicurarci la sua corretta realizzazione procediamo con le analisi nomi-verbo e la creazione delle schede CRC.

## 3. Attori e Casi d’Uso

### 3.1 Attori

Gli attori identificati sono visionabili in dettaglio nel documento dei modelli di caso d'uso

### 3.2 Casi d'uso 

I casi d'uso identificati sono visionabili in dettaglio nel documento dei modelli di caso d'uso, qui riporteremo solo gli ID 

## 4. Analisi Nomi-Verbi

L’approccio "nomi-verbi" prevede di identificare le entità principali (sostantivi) e le azioni (verbi) che il sistema deve supportare. Di seguito, alcune delle principali classi e operazioni estratte dall’analisi dei casi d’uso:

### 4.1 Entità (Nomi)
- **UtenteGenerico**: astrazione che rappresenta sia l’utente Guest sia l’utente autenticato.
- **Bibliotecario**: utente con privilegi amministrativi.
- **Libro**: oggetto ricercabile, in prestito o disponibile per il prestito.
- **Prestito**: operazione relativa al prestito fisico o digitale dei libri o ebook.
- **Tessera**: strumento per l’accesso a privilegi unici
- **Prenotazione**: richiesta di prenotazione di uno spazio comune.
- **Commento/Recensione**: feedback lasciato dagli utenti all’interno della sezione gamification.
- **Biblioteca**: rappresentazione della biblioteca per le notizie e gli spazi

### 4.2 Azioni (Verbi)
Le principali operazioni individuate sono:
- **Autenticare**: per gestire l’accesso al sistema (AU_1, AU_2).
- **Registrare**: per l’inserimento di nuovi utenti (AU_4).
- **Modificare**: per aggiornare password (AU_3) o profili (G_2).
- **Effettuare Logout**: per terminare la sessione (AU_5).
- **Richiedere Tessera**: per le operazioni di tesseramento (T_1, T_2, T_3, T_4, T_5).
- **Partecipare**: per accedere al sistema di gamification (G_1).
- **Commentare/Recensire**: per l’inserimento di feedback sui libri (G_3).
- **Segnalare**: per la gestione delle problematiche (G_4, PS_3).
- **Riscattare**: per il riscatto dei punti (G_5).
- **Ricercare**: per la ricerca dei libri e la richiesta di prestito (PL_1).
- **Restituire**: per la restituzione dei libri (PL_2).
- **Richiedere Allungamento**: per estendere il periodo di prestito (PL_3).
- **Richiedere e-book**: per il prestito digitale (PL_4).
- **Prenotare/Cancellare Prenotazione**: per la gestione delle prenotazioni degli spazi (PS_1, PS_2).
- **Caricare**: per l’inserimento di nuovi libri nel sistema (SA_1).
- **Segnalare Prestito e Notizie**: per aggiornare lo stato del sistema (SA_2, SA_3).
- **Gestire**: per la personalizzazione della pagina della biblioteca (SA_4).

## 5. Schede CRC

| Campo | Dettaglio |
|---|---| 
| **Nome**          | UtenteGenerico |
| **SuperClassi**   | - |
| **SottoClassi**   | - UtenteGuest <br/> - Utente <br/> - UtenteGamification |
| **Attributi**     | - |
| **Responsabilità**| - Effettuare l’autenticazione e la registrazione (login, logout). <br> - Effettuare ricerche <br/> - Visionare le pagine delle biblioteche |
| **Collaboratori** | - |

| Campo | Dettaglio |
|---|---| 
| **Nome**          | UtenteGuest |
| **SuperClassi**   | - UtenteGenerico |
| **SottoClassi**   | - |
| **Attributi**     | - |
| **Responsabilità**| - |
| **Collaboratori** | - |

| Campo | Dettaglio |
|---|---| 
| **Nome**          | Utente |
| **SuperClassi**   | - UtenteGenerico |
| **SottoClassi**   | - |
| **Attributi**     | - Nome <br/> - Cognome <br/> - Email <br/> - Numero di telefono <br/> - Numero Tessera  <br/>|
| **Responsabilità**| - Gestire la modifica del profilo, inclusa la modifica della password. <br> - Richiedere prestiti, tesseramenti e prenotazioni degli spazi. |
| **Collaboratori** | - Bibliotecario – per la gestione e approvazione delle richieste. <br> - Prestito – per l’attivazione e la gestione dei prestiti dei libri. <br> - Tessera – per l’iniziativa e il rinnovo del tesseramento. <br> - Prenotazione – per la richiesta e gestione delle prenotazioni degli spazi. |

| Campo | Dettaglio |
|---|---| 
| **Nome**          | UtenteGamification |
| **SuperClassi**   | - Utente |
| **SottoClassi**   | - |
| **Attributi**     | - Identifico Gamification <br/>        |
| **Responsabilità**| - Partecipare al sistema di gamification (inserimento commenti/recensioni, riscossione punti). <br>|
| **Collaboratori** | - Bibliotecario – per la verifica dei contenuti pubblicati. <br> |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Bibliotecario |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Nome <br/> - Cognome <br/> - Email <br/> - Numero di telefono <br/> - Identifico Lavorativo <br/> |
| **Responsabilità**| - Gestire la sezione amministrativa del sistema. <br> - Caricare nuovi libri e aggiornare il catalogo. <br> - Segnalare prestiti avvenuti (fisici o tramite API) e aggiornare lo stato dei libri in caso di cambiamenti non rilevabili dal sistema. <br> - Pubblicare e aggiornare le notizie riguardanti la biblioteca. <br> - Moderare i contenuti della sezione gamification, segnalando commenti o recensioni inappropriati. |
| **Collaboratori** | - Utente – per le interazioni relative a richieste e segnalazioni. <br> - Libro – per l’aggiornamento e la gestione del catalogo. <br> - Prestito – per la gestione delle operazioni di prestito e restituzione. <br> - Notizia – per l’inserimento e l’aggiornamento delle notizie. <br> - Prenotazione – per la conferma e la segnalazione delle prenotazioni. |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Libro |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Titolo <br/> - Identificativo libro  <br/> - Autore  <br/> - Lista biblioteche di appartenenza  <br/> - Disponibilità  <br/> - Genere |
| **Responsabilità**| - Memorizzare e fornire informazioni dettagliate (titolo, autore, genere, ecc.). <br> - Gestire lo stato di disponibilità per il prestito. <br> - Supportare la funzionalità di ricerca. |
| **Collaboratori** | - Prestito – per aggiornare lo stato durante le operazioni di prestito e restituzione. <br> - Bibliotecario – per il caricamento e l’aggiornamento dei dati nel sistema. |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Prestito |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Data Inizio  <br/> - Data fine  <br/> - Stato <br/> - Prenotazione |
| **Responsabilità**| - Attivare e gestire il ciclo di vita di un prestito (richiesta, attivazione, estensione, restituzione). <br> - Monitorare e aggiornare lo stato di un libro in prestito. |
| **Collaboratori** | - Utente – per l’iniziativa della richiesta di prestito. <br> - Libro – per modificare lo stato di disponibilità. <br> - Bibliotecario – per la gestione manuale (scannerizzazione, conferme) del prestito. |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Tessera  |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Numero Tessera  <br/> - Data di Emissione  <br/> - Scadenza <br/> - Stato |
| **Responsabilità**| - Gestire le operazioni di tesseramento (nuovo tesseramento, rinnovo, cancellazione). <br> - Gestire le denunce di smarrimento o furto della tessera. |
| **Collaboratori** | - Utente – per la richiesta e la gestione del proprio tesseramento. <br> - Bibliotecario – per la verifica e l’approvazione delle operazioni di tesseramento.  |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Prenotazione  |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Data inizio <br/> - Stato <br/> - Utente <br/> - Libro |
| **Responsabilità**| - Gestire la prenotazione degli spazi comuni. <br> - Consentire la cancellazione delle prenotazioni attive.      |
| **Collaboratori** | - Utente – per l’iniziativa della prenotazione. <br> - Bibliotecario – per la gestione delle risposte e per la segnalazione di eventuali errori. <br> - Biblioteca – per verificare la disponibilità degli ambienti da prenotare. |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Commento/Recensione |
| **SuperClassi**   | - |
| **SottoClassi**   | - |
| **Attributi**     | - Contenuto <br/> - Data creazione <br/> -Utente <br/> - Segnalazione <br/> - Lista commenti <br/> - Libro       |
| **Responsabilità**| - Memorizzare e visualizzare il feedback degli utenti sui libri. <br> - Consentire l’inserimento, la modifica e la segnalazione dei commenti. |
| **Collaboratori** | - Utente – per la creazione e la gestione dei propri commenti. <br> - Bibliotecario – per la moderazione e la rimozione dei contenuti inappropriati. |

| Campo | Dettaglio |
|---|---|
| **Nome**          | Biblioteca |
| **SuperClassi**   | -         |
| **SottoClassi**   | -         |
| **Attributi**     | - Nome <br/> - Indirizzo <br/> - Lista spazi disponibili <br/> - Lista notizie |
| **Responsabilità**| - Memorizzare, pubblicare e aggiornare le notizie riguardanti la biblioteca. <br> - Gestire la visualizzazione delle notizie sulla pagina della biblioteca. <br/> - Rappresentare gli spazi comuni prenotabili e gestirne la disponibilità |
| **Collaboratori** |  - Prenotazione – per la gestione delle richieste di prenotazione. <br> - Bibliotecario – per l’inserimento e l’aggiornamento delle notizie, nonché per l’aggiornamento e la manutenzione delle informazioni sugli spazi. |
