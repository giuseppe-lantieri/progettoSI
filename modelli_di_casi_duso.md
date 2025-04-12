# Biblioteche di Roma
### Modelli di Caso d'Uso

## Introduzione
In questo file vengono definiti i modelli di casi d'uso per il portale "Biblioteche di Roma". Tale documento ha lo scopo di descrivere in maniera dettagliata gli scenari di interazione tra gli attori e il sistema, fornendo una visione completa delle funzionalità offerte.

## Attori
Di seguito vengono elencati e descritti i possibili attori che interagiranno con il portale. Ogni attore viene caratterizzato dai seguenti parametri:
- **ID**: Identificativo unico dell'attore.
- **Nome**: Nome descrittivo dell'attore, comprensibile anche a utenti non tecnici.
- **Genitore**: Attore da cui ha avuto origine (se presente).
- **Tipo**: Tipologia dell'attore (ad es. primario o secondario) in base alle sue possibili interazioni.
- **Descrizione**: Breve descrizione che illustra la funzione dell'attore.

<!-- Tabella degli attori -->
| Campo        | Contenuto                                                                 |
|--------------|---------------------------------------------------------------------------|
| **ID**       | 1                                                                         |
| **Nome**     | UtenteGuest                                                               |
| **Genitore** | -                                                                         |
| **Tipo**     | Secondario                                                                |
| **Descrizione** | Utente che accede senza effettuare il login, con operazioni limitate.  |

| Campo        | Contenuto                                                                 |
|--------------|---------------------------------------------------------------------------|
| **ID**       | 2                                                                         |
| **Nome**     | Utente                                                                    |
| **Genitore** | UtenteGuest                                                               |
| **Tipo**     | Primario                                                                  |
| **Descrizione** | Utente che effettua il login, sbloccando funzionalità aggiuntive.       |

| Campo        | Contenuto                                                                 |
|--------------|---------------------------------------------------------------------------|
| **ID**       | 3                                                                         |
| **Nome**     | Bibliotecario                                                             |
| **Genitore** | -                                                                         |
| **Tipo**     | Primario                                                                  |
| **Descrizione** | Dipendente della biblioteca con elevati livelli di permessi per accedere alla sezione amministrativa. |

| Campo        | Contenuto                                                                 |
|--------------|---------------------------------------------------------------------------|
| **ID**       | 4                                                                         |
| **Nome**     | Servizio Esterno                                                          |
| **Genitore** | -                                                                         |
| **Tipo**     | Secondario                                                                |
| **Descrizione** | Servizio esterno che accede al portale tramite l’API dedicata.         |

## Casi d'Uso

I casi d'uso vengono organizzati in macro-gruppi (scenari), ciascuno identificato da un prefisso e numerati in modo univoco. Di seguito viene riportata la nomenclatura adottata per i vari scenari:

### AutenticazioneUtenti (AU)
- **AU_1**: Autenticazione Utente Sistema Interno  
- **AU_2**: Autenticazione Utente Tramite Sistema Esterno  
- **AU_3**: Modifica Password Sistema Interno  
- **AU_4**: Registrazione  
- **AU_5**: Logout

### Tesseramento (T)
- **T_1**: Nuovo Tesseramento  
- **T_2**: Rinnovo Tesseramento  
- **T_3**: Cancellazione Tesseramento  
- **T_4**: Denuncia Smarrimento Tesseramento  
- **T_5**: Denuncia Furto Tesseramento

### Gamification (G)
- **G_1**: Partecipazione al Sistema di Gamification  
- **G_2**: Gestione Profilo  
- **G_3**: Inserimento Commento/Recensione  
- **G_4**: Segnalazione Commento/Recensione  
- **G_5**: Riscatto Punti

### PrestitoLibri (PL)
- **PL_1**: Ricerca Libro Fisico e Richiesta di Prestito  
- **PL_2**: Restituzione Prestito Fisico  
- **PL_3**: Richiesta Allungamento Prestito Fisico  
- **PL_4**: Richiesta E-book

### PrenotazioneSpazio (PS)
- **PS_1**: Prenotazione di uno Spazio Comune  
- **PS_2**: Cancellazione di una Prenotazione  
- **PS_3**: Segnalazione Richiesta/Comportamento Errato

### Sezione Amministrativa (SA)
- **SA_1**: Caricamento Nuovi Libri  
- **SA_2**: Segnalazione Prestito Avvenuto Dal Vivo  
- **SA_3**: Segnalazione Notizie  
- **SA_4**: Gestione Pagina della Biblioteca

## Tabelle Descrittive dei Casi d'Uso
Di seguito vengono descritte le proprietà che caratterizzano ciascun caso d'uso:
- **ID**: Identificativo univoco del caso d'uso.
- **Nome**: Nome descrittivo del caso d'uso.
- **Priorità**: Valore (da 1 a 10) che esprime l'importanza e l'impatto del caso d'uso. MustHave (10-9),Should Have (8-7), Recommended (6-5),Would Be Better to Have (4-3),Optional (2-1)
- **Attori**: Elenco degli attori coinvolti.
- **Descrizione**: Breve descrizione del caso d'uso.
- **Condizioni**: Condizioni preliminari richieste al sistema.
- **Risultato**: Stato del sistema al termine del caso d'uso.
- **Flusso**: Descrizione dettagliata delle interazioni tra l'attore e il sistema.

<!-- Tabella dei casi d'uso -->

### Autenticazione Utenti

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | AU_1                                                                                                                   |
| **Nome**     | Autenticazione Utente Sistema Interno                                                                                  |
| **Priorità** | 10                                                                                                                     |
| **Attori**   | UtenteGuest, Utente                                                                                                    |
| **Descrizione** | Un utente si autentica tramite email e password registrate precedentemente.                                       |
| **Condizioni**  | L'utente deve essere già registrato.                                                                               |
| **Risultato**   | L'utente viene autenticato (trasformazione da UtenteGuest a Utente) oppure l'accesso viene negato.                   |
| **Flusso**      | 1. Selezione del pulsante di accesso. <br/> 2. Compilazione del form con email e password. <br/> 3. Il sistema verifica le credenziali. <br/> 4. In base al risultato: <br/> &nbsp;&nbsp;&nbsp;&nbsp;a. L'utente viene autenticato; <br/> &nbsp;&nbsp;&nbsp;&nbsp;b. L'autenticazione viene negata. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | AU_2                                                                                                                   |
| **Nome**     | Autenticazione Utente Tramite Sistema Esterno                                                                          |
| **Priorità** | 10                                                                                                                     |
| **Attori**   | UtenteGuest, Utente, Servizio Esterno                                                                                  |
| **Descrizione** | Un utente si autentica tramite un servizio esterno (ad es. CIE o SPID).                                             |
| **Condizioni**  | -                                                                                                                   |
| **Risultato**   | L'utente viene autenticato (trasformazione da UtenteGuest a Utente) oppure l'accesso viene negato.                   |
| **Flusso**      | 1. Selezione del pulsante corrispondente al servizio scelto. <br/> 2. Reindirizzamento alla pagina del servizio. <br/> 3. Il servizio esterno certifica l'utente e fornisce le informazioni necessarie. <br/> 4. Il sistema verifica la presenza dell'utente. <br/> 5. In base alla verifica: <br/> &nbsp;&nbsp;&nbsp;&nbsp;a. L'utente viene autenticato; <br/> &nbsp;&nbsp;&nbsp;&nbsp;b. Viene creato un nuovo utente e l'accesso è consentito. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | AU_3                                                                                                                   |
| **Nome**     | Modifica Password Sistema Interno                                                                                      |
| **Priorità** | 10                                                                                                                     |
| **Attori**   | UtenteGuest                                                                                                            |
| **Descrizione** | Un utente richiede di modificare la propria password.                                                               |
| **Condizioni**  | L'utente deve essere già registrato.                                                                               |
| **Risultato**   | L'utente aggiorna la password tramite il sistema.                                                                 |
| **Flusso**      | 1. Selezione del pulsante "Ho dimenticato la password". <br/> 2. Reindirizzamento a una pagina con un form per inserire l'email. <br/> 3. Invio di una password temporanea all'indirizzo email. <br/> 4. La password temporanea viene forzata nell'account. <br/> 5. Al successivo login, l'utente è tenuto a impostare una nuova password. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | AU_4                                                                                                                   |
| **Nome**     | Registrazione                                                                                                          |
| **Priorità** | 10                                                                                                                     |
| **Attori**   | UtenteGuest                                                                                                            |
| **Descrizione** | Un utente si registra tramite il servizio interno.                                                                  |
| **Condizioni**  | L'utente non deve essere registrato in precedenza.                                                                  |
| **Risultato**   | L'utenteGuest viene trasformato in un nuovo Utente.                                                               |
| **Flusso**      | 1. Selezione del pulsante "Registrami". <br/> 2. Reindirizzamento alla pagina di registrazione contenente un form per inserire email, dati anagrafici e password. <br/> 3. Il sistema salva in maniera sicura le informazioni nel database. <br/> 4. L'utente viene reindirizzato alla pagina di login. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | AU_5                                                                                                                   |
| **Nome**     | Logout                                                                                                                 |
| **Priorità** | 10                                                                                                                     |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente desidera chiudere la propria sessione.                                                                     |
| **Condizioni**  | L'utente deve essere autenticato.                                                                                  |
| **Risultato**   | L'utente viene disconnesso, ritornando allo stato di UtenteGuest.                                                   |
| **Flusso**      | 1. Selezione del pulsante "Logout". <br/> 2. Reindirizzamento alla pagina iniziale mentre il sistema invalida cookie e sessione. |

### Tesseramento

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | T_1                                                                                                                   |
| **Nome**     | Nuovo Tesseramento                                                                                                     |
| **Priorità** | 8                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede l'emissione della tessera.                                                                         |
| **Condizioni**  | L'utente non è in possesso di tessera.                                                                              |
| **Risultato**   | La richiesta di tesseramento viene inviata all'ufficio competente, che fornisce una ricevuta e l'indirizzo per il ritiro. |
| **Flusso**      | 1. Selezione del pulsante "Nuovo tesseramento". <br/> 2. Reindirizzamento a una pagina con form per compilare i dati anagrafici e selezionare il tier della tessera. <br/> 3. Il sistema verifica i dati e segnala eventuali errori. <br/> 4. La richiesta viene inoltrata all'ufficio competente e viene restituita una ricevuta. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | T_2                                                                                                                   |
| **Nome**     | Rinnovo Tesseramento                                                                                                   |
| **Priorità** | 5                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede il rinnovo della tessera.                                                                          |
| **Condizioni**  | L'utente è già in possesso di tessera.                                                                              |
| **Risultato**   | La richiesta di rinnovo viene inoltrata e una ricevuta viene restituita all'utente.                                  |
| **Flusso**      | 1. Selezione del pulsante "Rinnovo tesseramento". <br/> 2. Reindirizzamento alla pagina di rinnovo con un form che richiede il codice della tessera esistente. <br/> 3. Il sistema controlla i dati, segnala eventuali errori e inoltra la richiesta all'ufficio competente. <br/> 4. Viene fornita una ricevuta all'utente. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | T_3                                                                                                                   |
| **Nome**     | Cancellazione Tesseramento                                                                                             |
| **Priorità** | 7                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede la cancellazione della propria tessera.                                                          |
| **Condizioni**  | L'utente deve essere in possesso di tessera.                                                                         |
| **Risultato**   | La richiesta di cancellazione viene inoltrata e l'utente riceve una conferma.                                         |
| **Flusso**      | 1. Selezione del pulsante "Cancellazione tesseramento". <br/> 2. Reindirizzamento a una pagina con form per inserire il codice della tessera. <br/> 3. Il sistema verifica i dati, segnala eventuali errori e inoltra la richiesta. <br/> 4. Viene fornita una ricevuta di conferma. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | T_4                                                                                                                   |
| **Nome**     | Denuncia Smarrimento Tesseramento                                                                                      |
| **Priorità** | 8                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente denuncia lo smarrimento della tessera.                                                                      |
| **Condizioni**  | L'utente deve essere in possesso della tessera.                                                                      |
| **Risultato**   | La denuncia viene inoltrata all'ufficio competente e viene restituita una ricevuta.                                  |
| **Flusso**      | 1. Selezione del pulsante "Smarrimento tessera". <br/> 2. Reindirizzamento a una pagina con form per inserire il codice della tessera. <br/> 3. Il sistema verifica i dati, segnala eventuali errori e inoltra la richiesta. <br/> 4. Viene restituita una ricevuta. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | T_5                                                                                                                   |
| **Nome**     | Denuncia Furto Tesseramento                                                                                            |
| **Priorità** | 8                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente denuncia il furto della propria tessera.                                                                   |
| **Condizioni**  | L'utente deve essere in possesso della tessera.                                                                      |
| **Risultato**   | La denuncia viene inoltrata all'ufficio competente e viene restituita una ricevuta.                                  |
| **Flusso**      | 1. Selezione del pulsante "Smarrimento tessera". <br/> 2. Reindirizzamento a una pagina con form in cui l'utente allega la denuncia di furto. <br/> 3. Il sistema verifica i dati e segnala eventuali errori. <br/> 4. Il sistema inoltra la richiesta e restituisce una ricevuta. |

### Gamification

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | G_1                                                                                                                   |
| **Nome**     | Partecipazione al Sistema di Gamification                                                                              |
| **Priorità** | 3                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente si iscrive e partecipa al sistema di gamification del portale.                                              |
| **Condizioni**  | L'utente deve essere autenticato.                                                                                   |
| **Risultato**   | L'utente viene abilitato ad accedere alla sezione gamification.                                                     |
| **Flusso**      | 1. L'utente accede alla sezione dedicata alla gamification. <br/> 2. Seleziona il pulsante "Voglio partecipare al gioco". <br/> 3. Legge il regolamento e accetta le condizioni. <br/> 4. Il sistema registra la partecipazione e abilita l'accesso alla sezione. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | G_2                                                                                                                   |
| **Nome**     | Gestione Profilo                                                                                                       |
| **Priorità** | 3                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente desidera personalizzare il proprio profilo.                                                                |
| **Condizioni**  | L'utente deve già partecipare al sistema di gamification.                                                           |
| **Risultato**   | Le modifiche al profilo vengono applicate e salvate.                                                                 |
| **Flusso**      | 1. L'utente accede alla sezione "Profilo" all'interno della gamification. <br/> 2. Modifica i dati tramite i menu appositi. <br/> 3. Il sistema conferma le modifiche e aggiorna il profilo. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | G_3                                                                                                                   |
| **Nome**     | Inserimento Commento/Recensione                                                                                        |
| **Priorità** | 3                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente desidera lasciare una recensione o un commento su un libro.                                                  |
| **Condizioni**  | L'utente deve essere iscritto e partecipare al sistema di gamification.                                             |
| **Risultato**   | Il commento o la recensione viene aggiunto al sistema.                                                              |
| **Flusso**      | 1. L'utente seleziona il libro da recensire. <br/> 2. Clicca sul pulsante "Recensisci". <br/> 3. Inserisce il testo della recensione e conferma. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | G_4                                                                                                                   |
| **Nome**     | Segnalazione Commento/Recensione                                                                                       |
| **Priorità** | 3                                                                                                                      |
| **Attori**   | Bibliotecario                                                                                                          |
| **Descrizione** | Un bibliotecario vuole segnalare un commento o una recensione inappropriata.                                          |
| **Condizioni**  | L'utente ha pubblicato un commento o una recensione.                                                                 |
| **Risultato**   | Il commento o la recensione viene rimosso e, eventualmente, vengono applicate penalizzazioni all'utente.              |
| **Flusso**      | 1. Il bibliotecario individua il commento o la recensione problematica. <br/> 2. Seleziona il pulsante "Segnala". <br/> 3. Il sistema rimuove il contenuto e, se previsto, applica una decurtazione dei punti gamification. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | G_5                                                                                                                   |
| **Nome**     | Riscatto Punti                                                                                                         |
| **Priorità** | 1                                                                                                                      |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente desidera riscattare i punti accumulati per ottenere premi.                                                 |
| **Condizioni**  | L'utente deve partecipare al sistema di gamification e avere sufficiente punteggio.                                  |
| **Risultato**   | Viene effettuato il riscatto del premio e il punteggio viene aggiornato di conseguenza.                              |
| **Flusso**      | 1. L'utente accede alla sezione "Gamification". <br/> 2. Seleziona il pulsante "Riscatta Punti". <br/> 3. Sceglie il premio desiderato. <br/> 4. Il sistema elabora la richiesta, fornisce una ricevuta e aggiorna il punteggio. |

### Prestito Libri

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PL_1                                                                                                                  |
| **Nome**     | Ricerca Libro Fisico e Richiesta di Prestito                                                                            |
| **Priorità** | 9                                                                                                                     |
| **Attori**   | UtenteGuest, Utente                                                                                                   |
| **Descrizione** | Un utente (o utente non ancora autenticato) cerca e richiede il prestito di un libro fisico.                           |
| **Condizioni**  | Per completare la richiesta è necessario essere autenticati (trasformazione di UtenteGuest in Utente).                  |
| **Risultato**   | Viene effettuata la prenotazione del libro.                                                                          |
| **Flusso**      | 1. L'attore inserisce i termini di ricerca nella barra dedicata. <br/> 2. Il sistema presenta una lista di libri (almeno 50, con eventuali ulteriori risultati su richiesta). <br/> 3. Selezionando un libro, il sistema differenzia il flusso in base al ruolo: <br/> &nbsp;&nbsp;&nbsp;&nbsp;a. Per un Utente, viene offerta la possibilità di inviare la richiesta di prestito e viene indicata la biblioteca per il ritiro. <br/> &nbsp;&nbsp;&nbsp;&nbsp;b. Per un UtenteGuest, viene mostrato un banner che invita alla registrazione o all'autenticazione per poter procedere. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PL_2                                                                                                                  |
| **Nome**     | Restituzione Prestito Fisico                                                                                           |
| **Priorità** | 9                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Il bibliotecario comunica la restituzione di un libro attualmente in prestito.                                        |
| **Condizioni**  | Esiste un prestito attivo.                                                                                           |
| **Risultato**   | Il libro viene reso disponibile per un nuovo prestito.                                                               |
| **Flusso**      | 1. Il bibliotecario scannerizza il libro restituito. <br/> 2. Il sistema riceve tramite API l'informazione di restituzione. <br/> 3. Il libro viene aggiornato come disponibile. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PL_3                                                                                                                  |
| **Nome**     | Richiesta Allungamento Prestito Fisico                                                                                 |
| **Priorità** | 6                                                                                                                     |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede l'estensione del periodo di un prestito attivo.                                                    |
| **Condizioni**  | Esiste un prestito attivo.                                                                                           |
| **Risultato**   | Il sistema inoltra la richiesta di allungamento.                                                                     |
| **Flusso**      | 1. L'utente accede al proprio profilo e individua il prestito attivo, quindi seleziona "Allunga prestito". <br/> 2. Il sistema invia la richiesta all'ufficio competente. <br/> 3. L'utente viene informato tramite email sull'esito della richiesta. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PL_4                                                                                                                  |
| **Nome**     | Richiesta E-book                                                                                                      |
| **Priorità** | 4                                                                                                                     |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede la fruizione di un ebook.                                                                         |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | L'utente riceve l'accesso all'ebook, conformemente ai termini di licenza.                                             |
| **Flusso**      | 1. L'utente accede alla sezione dedicata agli ebook e ricerca il titolo desiderato. <br/> 2. Seleziona il pulsante "Prestito". <br/> 3. Accetta i termini e le condizioni. <br/> 4. Il sistema concede l’accesso all’ebook in base ai termini di utilizzo. |

### Prenotazione Spazio

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PS_1                                                                                                                  |
| **Nome**     | Prenotazione di uno Spazio Comune                                                                                      |
| **Priorità** | 3                                                                                                                     |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente richiede la prenotazione di uno spazio (ad esempio, una sala o un tavolo) presso una biblioteca.               |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | L'utente riceve una notifica via email con l'esito della prenotazione.                                               |
| **Flusso**      | 1. L'utente accede alla schermata delle prenotazioni della biblioteca scelta. <br/> 2. Il sistema invia una mail con i dettagli della richiesta all'indirizzo della biblioteca. <br/> 3. A seguito della risposta della biblioteca, il sistema comunica l'esito all'utente. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PS_2                                                                                                                  |
| **Nome**     | Cancellazione di una Prenotazione                                                                                      |
| **Priorità** | 2                                                                                                                     |
| **Attori**   | Utente                                                                                                                 |
| **Descrizione** | Un utente desidera cancellare una prenotazione attiva.                                                              |
| **Condizioni**  | Esiste una prenotazione attiva.                                                                                    |
| **Risultato**   | La prenotazione viene cancellata e l'utente riceve una notifica.                                                   |
| **Flusso**      | 1. L'utente accede alla sezione delle prenotazioni nel proprio profilo e seleziona "Cancella" per la prenotazione desiderata. <br/> 2. Il sistema invia una mail di conferma della cancellazione alla biblioteca. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | PS_3                                                                                                                  |
| **Nome**     | Segnalazione Richiesta/Comportamento Errato                                                                             |
| **Priorità** | 3                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Un bibliotecario desidera segnalare una richiesta o un comportamento errato relativo a una prenotazione.                 |
| **Condizioni**  | Esiste una prenotazione attiva.                                                                                    |
| **Risultato**   | Viene applicata una penalizzazione (ad es. decurtazione punti) all'utente coinvolto.                                  |
| **Flusso**      | 1. Il bibliotecario individua la prenotazione problematica. <br/> 2. Seleziona il pulsante "Segnala". <br/> 3. Il sistema applica le penalizzazioni previste. |

### Sezione Amministrativa

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | SA_1                                                                                                                  |
| **Nome**     | Caricamento Nuovi Libri                                                                                                |
| **Priorità** | 8                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Un bibliotecario desidera caricare un nuovo libro nel sistema.                                                       |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | Il nuovo libro viene aggiunto alla lista della biblioteca e reso disponibile sul portale.                            |
| **Flusso**      | 1. Il bibliotecario accede alla sezione amministrativa e seleziona "Aggiungi un libro". <br/> 2. Scannerizza il codice del libro e inserisce i dati richiesti. <br/> 3. Il sistema aggiorna il catalogo, rendendo il libro disponibile agli utenti. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | SA_2                                                                                                                  |
| **Nome**     | Segnalazione Prestito Avvenuto Dal Vivo                                                                                |
| **Priorità** | 8                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Un bibliotecario segnala che un prestito avvenuto in sede è stato completato.                                         |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | Lo stato del libro viene aggiornato, indicando che non è più in prestito.                                             |
| **Flusso**      | 1. Il bibliotecario accede alla sezione amministrativa e seleziona l'opzione per comunicare un prestito avvenuto. <br/> 2. Scannerizza il codice del libro e inserisce le informazioni relative al prestito. <br/> 3. Il sistema aggiorna lo stato del libro rendendolo disponibile per un nuovo prestito. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | SA_3                                                                                                                  |
| **Nome**     | Segnalazione Notizie                                                                                                   |
| **Priorità** | 8                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Un bibliotecario desidera segnalare notizie o aggiornamenti relativi alla propria biblioteca.                         |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | La sezione notizie della pagina della biblioteca viene aggiornata.                                                  |
| **Flusso**      | 1. Il bibliotecario accede alla sezione amministrativa e seleziona "Nuove notizie". <br/> 2. Compila il form per aggiungere o modificare le notizie. <br/> 3. Il sistema aggiorna la pagina della biblioteca di conseguenza. |

| Campo        | Contenuto                                                                                                              |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| **ID**       | SA_4                                                                                                                  |
| **Nome**     | Gestione Pagina della Biblioteca                                                                                       |
| **Priorità** | 6                                                                                                                     |
| **Attori**   | Bibliotecario                                                                                                         |
| **Descrizione** | Un bibliotecario desidera modificare l'aspetto e i contenuti della pagina della propria biblioteca.                     |
| **Condizioni**  | -                                                                                                                  |
| **Risultato**   | La pagina della biblioteca viene aggiornata in base alle modifiche apportate.                                        |
| **Flusso**      | 1. Il bibliotecario accede alla sezione amministrativa e seleziona "Modifica tema" o un'opzione simile. <br/> 2. Utilizza i menu appositi per personalizzare la pagina. <br/> 3. Il sistema aggiorna la pagina con le nuove impostazioni. |

<!-- Nota: Per migliorare la leggibilità delle tabelle, sono stati utilizzati tag HTML per gestire le interruzioni di riga all'interno delle celle. -->
