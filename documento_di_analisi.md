# Documento di Analisi – Gestione Biblioteche Romane

## 1. Introduzione
In questo documento viene descritta l’analisi del sistema per la gestione delle biblioteche romane. Il testo si articola in diverse sezioni:  
- Una descrizione preliminare del sistema;  
- L’analisi dei casi d’uso e la definizione del glossario;  
- L’estrazione delle classi di analisi tramite le schede CRC;  
- La rappresentazione delle relazioni mediante diagrammi EBC;  
- Infine, i diagrammi di sequenza.

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
L’approccio “nomi-verbi” prevede di identificare le entità principali (sostantivi) e le azioni (verbi) che il sistema deve supportare. Di seguito sono elencate alcune delle principali entità e operazioni, estratte dall’analisi dei casi d’uso.

### 4.1 Entità (Nomi)
- **Utente**: astrazione che rappresenta l’Utente autenticato.
- **Bibliotecario**: utente con privilegi amministrativi.
- **Libro**: oggetto ricercabile, in prestito o disponibile per il prestito.
- **Prestito**: operazione relativa al prestito fisico o digitale dei libri (o ebook).
- **Tessera**: strumento che consente l’accesso a privilegi particolari.
- **Prenotazione**: richiesta di prenotazione per uno spazio comune.
- **Commento/Recensione**: feedback lasciato dagli utenti all’interno della sezione di gamification.
- **Biblioteca**: rappresentazione dell’istituzione, per la pubblicazione di notizie e la gestione degli spazi.

### 4.2 Azioni (Verbi)
Le principali operazioni individuate sono:
- **Autenticare**: gestire l’accesso al sistema (AU_1, AU_2).
- **Registrare**: inserimento di nuovi utenti (AU_4).
- **Modificare**: aggiornare password (AU_3) o profili (G_2).
- **Effettuare Logout**: terminare una sessione (AU_5).
- **Richiedere Tessera**: gestire le operazioni di tesseramento (T_1, T_2, T_3, T_4, T_5).
- **Partecipare**: iscriversi al sistema di gamification (G_1).
- **Commentare/Recensire**: inserire feedback sui libri (G_3).
- **Segnalare**: gestire problematiche (G_4, PS_3).
- **Riscattare**: riscattare punti (G_5).
- **Ricercare**: cercare libri e richiedere il prestito (PL_1).
- **Restituire**: restituire i libri (PL_2).
- **Richiedere Allungamento**: estendere il periodo di prestito (PL_3).
- **Richiedere e-book**: ottenere prestito digitale (PL_4).
- **Prenotare/Cancellare Prenotazione**: gestire le prenotazioni degli spazi (PS_1, PS_2).
- **Caricare**: inserire nuovi libri nel sistema (SA_1).
- **Segnalare Prestito e Notizie**: aggiornare lo stato del sistema (SA_2, SA_3).
- **Gestire**: personalizzare la pagina della biblioteca (SA_4).

## 5. Schede CRC

## 1. Boundary

### 1.1 `UIAutenticazione`
**TipoClasse**: Boundary

| Campo | Dettaglio |
| --- | --- |
| **Nome**| UIAutenticazione |
| **Attributi**| - |
| **Responsabilità**| - Gestire autenticazione tramite login, logout<br/> - Gestire registrazione di nuovi utenti |
| **Collaboratori** | - CServiziEsterni<br/> - CUtenza |

### 1.2 `UIGuest`
**TipoClasse**: Boundary

| Campo | Dettaglio |
| --- | --- |
| **Nome**| UIGuest |
| **Attributi**| - |
| **Responsabilità**| - Effettuare ricerche<br/> - Visionare pagine disponibili:<br/> - cataloghi<br/> - news |
| **Collaboratori** | - CRicerche |

### 1.3 `UIUtente`
**TipoClasse**: Boundary

| Campo | Dettaglio |
| --- | --- |
| **Nome**| UIUtente |
| **Attributi**| - |
| **Responsabilità**| - Modificare profilo <br/> |
| **Collaboratori** | - CUtenza |

### 1.4 `UIGamification`
**TipoClasse**: Boundary

| Campo | Dettaglio |
| --- | --- |
| **Nome**| UIGamification |
| **Attributi**| - |
| **Responsabilità**| - Partecipare al sistema di gamification:<br/> - inserire commenti/recensioni<br/> - riscattare premi<br/> |
| **Collaboratori** | - CGamification |

### 1.5 `UIAmministrativa`
**TipoClasse**: Boundary

| Campo | Dettaglio |
| --- | ---|
| **Nome**| UIAmministrativa |
| **Attributi**| - |
| **Responsabilità**| - Caricare libri<br/> - Aggiornare catalogo<br/> - Segnalare prestiti<br/> - Moderare contenuti<br/> - Pubblicare notizie |
| **Collaboratori** | - CAmministrativo |

## 2. Control

### 2.1 `CAmministrativo`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CAmministrativo |
| **Attributi**| - |
| **Responsabilità**| - Eseguire le operazioni di gestione su comando di UIAmministrativa:<br/> - aggiunta libri<br/> - gestione prestiti<br/> - notizie<br/> - moderazione |
| **Collaboratori** | - EBibliotecario<br/> - ELibro<br/> - EPrestito<br/> - EBiblioteca |

### 2.2 `CServiziEsterni`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CServiziEsterni |
| **Attributi**| - |
| **Responsabilità**| - Eseguire le operazioni di gestione dei vari servizi esterni che potranno essere collegati |
| **Collaboratori** | - EUtente |

### 2.3 `CUtenza`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CUtenza |
| **Attributi**| - |
| **Responsabilità**| - Eseguire le operazioni di gestione degli utenti |
| **Collaboratori** | - EUtente |

### 2.4 `CPrenotazioni`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CPrenotazioni |
| **Attributi**| - |
| **Responsabilità**| - Coordinare le operazioni relative alla prenotazione e assicurare coerenza |
| **Collaboratori** | - EBibliotecario<br/> - ELibro<br/> - EPrestito<br/> - EBiblioteca - EUtente |

### 2.5 `CGamification`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CGamification |
| **Attributi**| - |
| **Responsabilità**| - Coordinare le operazioni relative alla gamification |
| **Collaboratori** | - EUtenteGamification<br/> -EFeedback |


### 2.6 `CRicerche`
**TipoClasse**: Control

| Campo | Dettaglio |
| --- | --- |
| **Nome**| CRicerche |
| **Attributi**| - |
| **Responsabilità**| - Responsabile per la ricerca dei libri |
| **Collaboratori** | - ELibro<br/> - EBiblioteca - EPrenotazione |

## 3. Entity

### 3.1 `EUtente`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EUtente |
| **Attributi**| - ID Utente<br/> - Nome<br/> - Cognome<br/> - Email<br/> - Numero di telefono<br/> - Numero Tessera |
| **Responsabilità**| - Mantenere i dati anagrafici e di contatto dell’utente |
| **Collaboratori** | - EPrestito<br/> - ETessera |

### 3.2 `EUtenteGamification`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EUtenteGamification |
| **SuperClassi** | EUtente |
| **Attributi**| - Identificativo Gamification<br/> - punti<br/> - statistiche<br/>  |
| **Responsabilità**| - Mantenere i dati relativi alla gamification |
| **Collaboratori** | - EFeedback<br/> |

### 3.3 `EBibliotecario`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EBibliotecario |
| **Attributi**| - Identificativo Lavorativo<br/> - Log azioni |
| **Responsabilità**| - Mantenere dati anagrafici del bibliotecario<br/> - Tracciare le azioni svolte come log |
| **Collaboratori** | - |

### 3.4 `ELibro`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| ELibro|
| **Attributi**| - Titolo<br/> - Identificativo Libro<br/> - Autore<br/> - Disponibilità<br/> - Genere |
| **Responsabilità**| - Memorizzare e fornire info <br/> - Gestire disponibilità<br/> - Supportare la ricerca |
| **Collaboratori** | - EPrestito <br/> - CBibliotecario |

### 3.5 `EPrestito`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EPrestito |
| **Attributi**| - Data Inizio<br/> - Data Fine<br/> - Stato<br/> - Riferimento a EUtente/Tessera<br/> - Riferimento a ELibro |
| **Responsabilità**| - Gestire il ciclo di vita di un prestito:<br/> - richiesta<br/> - attivazione<br/> - estensione<br/> - restituzione<br/> - Monitorare e aggiornare lo stato |
| **Collaboratori** | - EUtente <br/> - ELibro<br/> - CBibliotecario |

### 3.6 `ETessera`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| ETessera |
| **Attributi**| - Numero Tessera<br/> - Data di Emissione<br/> - Scadenza<br/> - Stato |
| **Responsabilità**| - Mantenere i dati del tesseramento |
| **Collaboratori** | - EUtente<br/> - CBibliotecario |

### 3.7 `EPrenotazione`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EPrenotazione |
| **Attributi**| - Id<br/>  - Data Inizio<br/> - Stato<br/> - Durata Prenotazione<br/> - Riferimento a EUtente<br/> - Riferimento a ELibro<br/> |
| **Responsabilità**| - Gestire prenotazioni:<br/> - richiesta<br/> - cancellazione |
| **Collaboratori** | - EUtente<br/> - EBibliotecario<br/> - EBiblioteca |

### 3.8 `EFeedback`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EFeedback |
| **Attributi**| - Contenuto<br/> - Data Creazione<br/> - Segnalazione<br/> - Riferimento a EUtente - Riferimento a ELibro <br/> - Riferimento a EFeedback |
| **Responsabilità**| - Memorizzare e visualizzare feedback utenti<br/> |
| **Collaboratori** | - EUtente<br/> - CBibliotecario |

### 3.9 `EBiblioteca`
**TipoClasse**: Entity

| Campo | Dettaglio |
| --- | --- |
| **Nome**| EBiblioteca |
| **Attributi**| - Nome<br/> - Indirizzo<br/> - Lista Spazi Disponibili<br/> - Lista Notizie - Lista Libri |
| **Responsabilità**| - Memorizzare, pubblicare e aggiornare notizie<br/> - Gestire spazi prenotabili |
| **Collaboratori** | - EPrenotazione<br/> - CBibliotecario |