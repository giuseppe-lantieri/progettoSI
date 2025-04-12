# Documento di Analisi – Gestione Biblioteche Romane

## 1. Introduzione
In questo documento viene descritta l’analisi del sistema per la gestione delle biblioteche romane. Il testo si articola in diverse sezioni:  
- Una descrizione preliminare del sistema;  
- L’analisi dei casi d’uso e la definizione del glossario;  
- L’estrazione delle classi di analisi tramite le schede CRC;  
- La rappresentazione delle relazioni mediante diagrammi EBC;  
- I diagrammi di sequenza.

## 2. Visione di Sistema
Il portale si configura come un sistema centralizzato, in grado di garantire la comunicazione tra diversi attori:

- **UtenteGuest** e **Utente**: Utenti finali che interagiscono con il sistema per cercare libri, effettuare prestiti, prenotare spazi e partecipare alle attività di gamification.  
- **Bibliotecario**: Operatore dotato di privilegi amministrativi, responsabile della gestione del catalogo, del monitoraggio dei prestiti e della pubblicazione di notizie.  
- **Servizio Esterno**: Sistema di integrazione con servizi di autenticazione esterni (ad es. CIE, SPID) che agevola l’accesso al portale.

La piattaforma garantisce una gestione centralizzata e sicura delle operazioni; per una corretta realizzazione, si procederà con l’analisi dei nomi e dei verbi e con la creazione delle schede CRC.

## 3. Attori e Casi d’Uso

### 3.1 Attori
Gli attori identificati sono desumibili in dettaglio dal documento dei modelli di caso d’uso.

### 3.2 Casi d’Uso
I casi d’uso sono descritti in maniera approfondita nel documento dei modelli di caso d’uso; in questa sezione si riportano solo gli identificativi (ID).

## 4. Analisi Nomi-Verbi
L’approccio “nomi-verbi” prevede di identificare le entità principali (nomi) e le azioni (verbi) che il sistema deve supportare. Di seguito sono elencate alcune delle principali entità e operazioni, estratte dall’analisi dei casi d’uso.

### 4.1 Entità (Nomi)
- **UtenteGenerico**: astrazione che rappresenta sia l’UtenteGuest che l’Utente autenticato.
- **Bibliotecario**: utente con privilegi amministrativi.
- **Libro**: oggetto ricercabile, disponibile o meno per il prestito.
- **Prestito**: operazione relativa al prestito fisico o digitale(o ebook) dei libri.
- **Tessera**: strumento di identificazione che consente l’accesso a privilegi particolari.
- **Prenotazione**: richiesta di utilizzo di uno spazio comune.
- **Commento/Recensione**: feedback lasciato dagli utenti all’interno della sezione di gamification.
- **Biblioteca**: rappresentazione dell’istituzione, per la pubblicazione di notizie e la gestione degli spazi.

### 4.2 Azioni (Verbi)
Le principali operazioni individuate sono:
- **Autenticare**: gestioje dell’accesso al sistema (AU_1, AU_2).
- **Registrare**: inserimento di nuovi utenti (AU_4).
- **Modificare**: aggiornamento di password (AU_3) o profili (G_2).
- **Effettuare Logout**: terminare una sessione (AU_5).
- **Richiedere Tessera**: gestione delle operazioni di tesseramento (T_1, T_2, T_3, T_4, T_5).
- **Partecipare**: iscrizione al sistema di gamification (G_1).
- **Commentare/Recensire**: inserimento di feedback sui libri (G_3).
- **Segnalare**: gestione di problematiche (G_4, PS_3).
- **Riscattare**: riscatto dei punti (G_5).
- **Ricercare**: ricerca di libri e richiesta di prestito (PL_1).
- **Restituire**: restituzione di libri (PL_2).
- **Richiedere Allungamento**: estensione del periodo di prestito (PL_3).
- **Richiedere e-book**: ottenimento di prestito digitale (PL_4).
- **Prenotare/Cancellare Prenotazione**: gestione delle prenotazioni degli spazi (PS_1, PS_2).
- **Caricare**: inserimento di nuovi libri nel sistema (SA_1).
- **Segnalare Prestito e Notizie**: aggiornamento dello stato del sistema (SA_2, SA_3).
- **Gestire**: personalizzazione della pagina della biblioteca (SA_4).

## 5. Schede CRC

### UtenteGenerico

| Campo              | Dettaglio                                                                                                                                                                  |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | UtenteGenerico                                                                                                                                                              |
| **SuperClassi**    | -                                                                                                                                                                           |
| **SottoClassi**    | UtenteGuest <br/> Utente <br/> UtenteGamification                                                                                                                          |
| **Attributi**      | -                                                                                                                                                                           |
| **Responsabilità** | Effettuare l’autenticazione e la registrazione (login, logout); <br/> Effettuare ricerche; <br/> Visionare le pagine delle biblioteche.                                    |
| **Collaboratori**  | -                                                                                                                                                                           |

### UtenteGuest

| Campo              | Dettaglio                                               |
|--------------------|----------------------------------------------------------|
| **Nome**           | UtenteGuest                                             |
| **SuperClassi**    | UtenteGenerico                                          |
| **SottoClassi**    | -                                                        |
| **Attributi**      | -                                                        |
| **Responsabilità** | -                                                        |
| **Collaboratori**  | -                                                        |

### Utente

| Campo              | Dettaglio                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Utente                                                                                                                                      |
| **SuperClassi**    | UtenteGenerico                                                                                                                              |
| **SottoClassi**    | -                                                                                                                                           |
| **Attributi**      | Nome <br/> Cognome <br/> Email <br/> Numero di telefono <br/> Numero Tessera                                                                  |
| **Responsabilità** | Gestire la modifica del profilo, inclusa la modifica della password; <br/> Richiedere prestiti, tesseramenti e prenotazioni degli spazi.   |
| **Collaboratori**  | Bibliotecario (per la gestione e approvazione delle richieste); <br/> Prestito (per l’attivazione e la gestione dei prestiti); <br/> Tessera (per l’iniziativa e il rinnovo); <br/> Prenotazione (per la gestione delle prenotazioni). |

### UtenteGamification

| Campo              | Dettaglio                                                                                                          |
|--------------------|---------------------------------------------------------------------------------------------------------------------|
| **Nome**           | UtenteGamification                                                                                                  |
| **SuperClassi**    | Utente                                                                                                              |
| **SottoClassi**    | -                                                                                                                   |
| **Attributi**      | Identificativo Gamification                                                                                         |
| **Responsabilità** | Partecipare al sistema di gamification (inserimento commenti/recensioni, riscossione punti).                         |
| **Collaboratori**  | Bibliotecario (per la verifica dei contenuti pubblicati).                                                           |

### Bibliotecario

| Campo              | Dettaglio                                                                                                                                       |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Bibliotecario                                                                                                                                   |
| **SuperClassi**    | -                                                                                                                                                |
| **SottoClassi**    | -                                                                                                                                                |
| **Attributi**      | Nome <br/> Cognome <br/> Email <br/> Numero di telefono <br/> Identificativo Lavorativo                                                          |
| **Responsabilità** | Gestire la sezione amministrativa del sistema; <br/> Caricare nuovi libri e aggiornare il catalogo; <br/> Segnalare prestiti e aggiornare lo stato dei libri; <br/> Pubblicare e aggiornare notizie; <br/> Moderare i contenuti nella sezione gamification. |
| **Collaboratori**  | Utente (per le interazioni relative a richieste e segnalazioni); <br/> Libro (per l’aggiornamento del catalogo); <br/> Prestito (per la gestione delle operazioni di prestito); <br/> Notizia (per l’inserimento e l’aggiornamento); <br/> Prenotazione (per la gestione delle prenotazioni). |

### Libro

| Campo              | Dettaglio                                                                                                                                   |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Libro                                                                                                                                       |
| **SuperClassi**    | -                                                                                                                                           |
| **SottoClassi**    | -                                                                                                                                           |
| **Attributi**      | Titolo <br/> Identificativo libro <br/> Autore <br/> Lista delle biblioteche di appartenenza <br/> Disponibilità <br/> Genere                        |
| **Responsabilità** | Memorizzare e fornire informazioni dettagliate (titolo, autore, genere, ecc.); <br/> Gestire lo stato di disponibilità; <br/> Supportare la funzione di ricerca. |
| **Collaboratori**  | Prestito (per aggiornare lo stato durante le operazioni di prestito); <br/> Bibliotecario (per il caricamento e l’aggiornamento dei dati).         |

### Prestito

| Campo              | Dettaglio                                                                                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Prestito                                                                                                                                     |
| **SuperClassi**    | -                                                                                                                                            |
| **SottoClassi**    | -                                                                                                                                            |
| **Attributi**      | Data Inizio <br/> Data Fine <br/> Stato <br/> Prenotazione                                                                                     |
| **Responsabilità** | Attivare e gestire il ciclo di vita di un prestito (richiesta, attivazione, estensione, restituzione); <br/> Monitorare e aggiornare lo stato.   |
| **Collaboratori**  | Utente (per l’iniziativa della richiesta di prestito); <br/> Libro (per modificare lo stato di disponibilità); <br/> Bibliotecario (per la gestione manuale del prestito). |

### Tessera

| Campo              | Dettaglio                                                                                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Tessera                                                                                                                                      |
| **SuperClassi**    | -                                                                                                                                            |
| **SottoClassi**    | -                                                                                                                                            |
| **Attributi**      | Numero Tessera <br/> Data di Emissione <br/> Scadenza <br/> Stato                                                                              |
| **Responsabilità** | Gestire le operazioni di tesseramento (nuovo tesseramento, rinnovo, cancellazione); <br/> Gestire le denunce di smarrimento o furto.         |
| **Collaboratori**  | Utente (per la richiesta e la gestione del tesseramento); <br/> Bibliotecario (per la verifica e l’approvazione delle operazioni).             |

### Prenotazione

| Campo              | Dettaglio                                                                                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Prenotazione                                                                                                                                 |
| **SuperClassi**    | -                                                                                                                                            |
| **SottoClassi**    | -                                                                                                                                            |
| **Attributi**      | Data Inizio <br/> Stato <br/> Utente <br/> Libro                                                                                              |
| **Responsabilità** | Gestire la prenotazione degli spazi comuni; <br/> Consentire la cancellazione delle prenotazioni attive.                                       |
| **Collaboratori**  | Utente (per l’iniziativa della prenotazione); <br/> Bibliotecario (per la gestione delle risposte e per la segnalazione di eventuali errori); <br/> Biblioteca (per verificare la disponibilità degli spazi).  |

### Commento/Recensione

| Campo              | Dettaglio                                                                                                                                 |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Commento/Recensione                                                                                                                        |
| **SuperClassi**    | -                                                                                                                                         |
| **SottoClassi**    | -                                                                                                                                         |
| **Attributi**      | Contenuto <br/> Data Creazione <br/> Utente <br/> Segnalazione <br/> Lista Commenti <br/> Libro                                            |
| **Responsabilità** | Memorizzare e visualizzare il feedback degli utenti sui libri; <br/> Consentire l’inserimento, la modifica e la segnalazione dei commenti. |
| **Collaboratori**  | Utente (per la creazione e la gestione dei commenti); <br/> Bibliotecario (per la moderazione e la rimozione dei contenuti inappropriati). |

### Biblioteca

| Campo              | Dettaglio                                                                                                                                 |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**           | Biblioteca                                                                                                                                |
| **SuperClassi**    | -                                                                                                                                         |
| **SottoClassi**    | -                                                                                                                                         |
| **Attributi**      | Nome <br/> Indirizzo <br/> Lista Spazi Disponibili <br/> Lista Notizie                                                                      |
| **Responsabilità** | Memorizzare, pubblicare e aggiornare le notizie relative alla biblioteca; <br/> Gestire la visualizzazione delle notizie; <br/> Gestire gli spazi prenotabili e la loro disponibilità. |
| **Collaboratori**  | Prenotazione (per la gestione delle richieste di prenotazione); <br/> Bibliotecario (per l’inserimento e l’aggiornamento delle notizie e degli spazi). |
