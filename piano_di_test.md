# Piano di Test del Progetto Biblioteche di Roma

## Scopo del Documento
Il presente documento descrive il piano di test finalizzato alla validazione dei seguenti casi d’uso del sistema. Le prove coprono tutte le funzionalità critiche, assicurando che le operazioni del portale rispondano agli standard e alle specifiche richieste.

## Prerequisiti Generali
- Connessione internet attiva.
- Utenza di amministrazione pre-esistente.
- Archivio dei libri da prenotare già caricato nel sistema.
- Utenza Bibliotecario pre-esistente.
- Servizio Wi-Fi funzionante.
- Funzione di localizzazione della posizione impostata tramite browser.

---

## Elenco dei Casi d'Uso

### Autenticazione Utenti (AU)
- **AU_1**: Autenticazione Utente Sistema Interno  
- **AU_2**: Autenticazione Utente tramite Sistema Esterno  
- **AU_3**: Modifica Password Sistema Interno  
- **AU_4**: Login (Registrazione)  
- **AU_5**: Logout

---

### Test dei Casi d'Uso

#### TestAU_1 - Autenticazione Utente Sistema Interno
| **Campo**          | **Dettaglio**                                                                                                                                                                                                |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica dell'autenticazione tramite il sistema interno.                                                                                                                                                     |
| **Pre-condizioni** | L'utente deve essere già registrato correttamente dal servizio.                                                                                                                                             |
| **Azioni**         | 1. Selezione del pulsante di accesso.<br/> 2. Compilazione del form con email e password.<br/> 3a. Il sistema autentica l'utente.<br/> 3b. In alternativa, il sistema rigetta l'autenticazione. |
| **Post-condizioni**| L'utenteGuest diventa Utente in caso di autenticazione positiva oppure l’accesso viene negato.                                                                                                                 |

---

#### TestAU_2 - Autenticazione Utente tramite Sistema Esterno
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                   |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica dell'autenticazione tramite un servizio esterno (ad es. CIE o SPID).                                                                                                                                                                                                                    |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                                                |
| **Azioni**         | 1. Selezione del pulsante relativo al servizio esterno scelto.<br/> 2. Reindirizzamento alla pagina del servizio.<br/> 3. Il sistema esterno certifica l'utente rilasciando le informazioni necessarie.<br/> 4. Il sistema verifica la presenza dell’utente.<br/> 5a. Autenticazione positiva; 5b. Creazione di un nuovo utente se necessario. |
| **Post-condizioni**| L'utenteGuest viene trasformato in Utente in caso di autenticazione positiva oppure l’accesso viene negato.                                                                                                                                                                                     |

---

#### TestAU_3 - Modifica Password Sistema Interno
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                              |
|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica la procedura di modifica della password per il sistema interno.                                                                                                                                                                                                                  |
| **Pre-condizioni** | L'utente deve essere già registrato.                                                                                                                                                                                                                                                      |
| **Azioni**         | 1. Selezione del pulsante "Ho dimenticato la password".<br/> 2. Reindirizzamento a una pagina contenente un form per l’inserimento dell’email.<br/> 3. Il sistema invia una password temporanea all'indirizzo email dell’utente.<br/> 4. Il sistema imposta la password temporanea nell’account.<br/> 5. Al successivo login, l’utente è tenuto a impostare una nuova password. |
| **Post-condizioni**| L'utenteGuest aggiorna la password e diventa Utente, con la nuova credenziale.                                                                                                                                                                                                              |

---

#### TestAU_4 - Registrazione (Login)
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                             |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di registrazione e successivo login.                                                                                                                                                                                                                 |
| **Pre-condizioni** | L'utente non deve essere registrato precedentemente.                                                                                                                                                                                                                     |
| **Azioni**         | 1. Selezione del pulsante "Registrami".<br/> 2. Reindirizzamento alla pagina di registrazione con form per email, dati anagrafici e scelta della password.<br/> 3. Il sistema salva in modo sicuro le informazioni nel database.<br/> 4. L'utente viene reindirizzato alla pagina di login per effettuare l’accesso. |
| **Post-condizioni**| L'utenteGuest diventa un nuovo Utente in seguito alla registrazione.                                                                                                                                                                                                       |

---

#### TestAU_5 - Logout
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                            |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura di logout.                                                                                                                                                                                                                     |
| **Pre-condizioni** | L'utente deve essere autenticato.                                                                                                                                                                                                                        |
| **Azioni**         | 1. Selezione del pulsante "Logout".<br/> 2. Reindirizzamento alla pagina iniziale del sito, con invalidazione dei cookie e della sessione da parte del sistema.                                                                                     |
| **Post-condizioni**| L'utente autenticato viene disconnesso e torna allo stato di UtenteGuest.                                                                                                                                                                               |

---

### Tesseramento (T)
- **T_1**: Nuovo Tesseramento  
- **T_2**: Rinnovo Tesseramento  
- **T_3**: Cancellazione Tesseramento  
- **T_4**: Denuncia Smarrimento Tesseramento  
- **T_5**: Denuncia Furto Tesseramento

#### TestT_1 - Nuovo Tesseramento
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                       |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di richiesta di nuovo tesseramento.                                                                                                                                                                                                                                                          |
| **Pre-condizioni** | L'utente non deve essere in possesso di tessera.                                                                                                                                                                                                                                                                     |
| **Azioni**         | 1. Selezione del pulsante "Nuovo tesseramento".<br/> 2. Reindirizzamento a una pagina contenente un form che richiede l'anagrafica e la scelta del tier della tessera.<br/> 3. Il sistema controlla i campi e segnala eventuali errori.<br/> 4. L'utente invia il form e riceve la ricevuta e l'indirizzo della biblioteca per il ritiro.               |
| **Post-condizioni**| L'utente invia correttamente la richiesta di tesseramento.                                                                                                                                                                                                                                                         |

---

#### TestT_2 - Rinnovo Tesseramento
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                        |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di rinnovo della tessera.                                                                                                                                                                                                                                                                      |
| **Pre-condizioni** | L'utente deve essere in possesso di una tessera esistente.                                                                                                                                                                                                                                                         |
| **Azioni**         | 1. Selezione del pulsante "Rinnovo tesseramento".<br/> 2. Reindirizzamento a una pagina con un form che richiede il codice della tessera esistente.<br/> 3. Il sistema verifica i dati inseriti, segnalando eventuali errori.<br/> 4. L'utente invia il form e riceve la ricevuta di rinnovo.                                                          |
| **Post-condizioni**| La richiesta di rinnovo viene inviata correttamente e l'utente riceve la conferma.                                                                                                                                                                                                                                  |

---

#### TestT_3 - Cancellazione Tesseramento
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                           |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di cancellazione della tessera.                                                                                                                                                                                                                                                                |
| **Pre-condizioni** | L'utente deve essere in possesso di una tessera.                                                                                                                                                                                                                                                                       |
| **Azioni**         | 1. Selezione del pulsante "Cancellazione tesseramento".<br/> 2. Reindirizzamento a una pagina con un form che richiede il codice della tessera.<br/> 3. Il sistema verifica i campi e segnala eventuali errori.<br/> 4. L'utente invia il form e riceve la ricevuta di conferma della cancellazione.                             |
| **Post-condizioni**| La richiesta di cancellazione viene elaborata correttamente.                                                                                                                                                                                                                                                          |

---

#### TestT_4 - Denuncia Smarrimento Tesseramento
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                        |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di denuncia di smarrimento della tessera.                                                                                                                                                                                                                                                     |
| **Pre-condizioni** | L'utente deve essere in possesso di una tessera.                                                                                                                                                                                                                                                                     |
| **Azioni**         | 1. Selezione del pulsante "Smarrimento tessera".<br/> 2. Reindirizzamento a una pagina con un form per l'inserimento del codice della tessera.<br/> 3. Il sistema controlla i dati, segnalando eventuali errori.<br/> 4. L'utente invia il form e riceve una ricevuta di conferma.                                   |
| **Post-condizioni**| La denuncia di smarrimento viene registrata nel sistema.                                                                                                                                                                                                                                                             |

---

#### TestT_5 - Denuncia Furto Tesseramento
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                              |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di denuncia di furto della tessera.                                                                                                                                                                                                                                                                 |
| **Pre-condizioni** | L'utente deve essere in possesso di una tessera.                                                                                                                                                                                                                                                                          |
| **Azioni**         | 1. Selezione del pulsante "Smarrimento tessera" (utilizzato anche per la denuncia furto).<br/> 2. Reindirizzamento a una pagina con form in cui l'utente allega la denuncia di furto emessa dall'ordine competente.<br/> 3. Il sistema verifica i dati e segnala eventuali errori.<br/> 4. L'utente invia il form e riceve una ricevuta. |
| **Post-condizioni**| La denuncia di furto viene registrata correttamente nel sistema.                                                                                                                                                                                                                                                         |

---

### Gamification (G)
- **G_1**: Partecipazione al Sistema di Gamification  
- **G_2**: Gestione Profilo  
- **G_3**: Inserimento Commento/Recensione  
- **G_4**: Segnalazione Commento/Recensione  
- **G_5**: Riscatto Punti

#### TestG_1 - Partecipazione al Sistema di Gamification
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                                                         |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di partecipazione al sistema di gamification.                                                                                                                                                                                                                                                   |
| **Pre-condizioni** | L'utente deve essere già registrato.                                                                                                                                                                                                                                                                                   |
| **Azioni**         | 1. L'utente accede alla sezione gamification.<br/> 2. Seleziona il pulsante "Voglio partecipare al gioco".<br/> 3. Legge il regolamento e accetta le condizioni.<br/> 4. Il sistema registra la partecipazione e abilita l'accesso alla sezione.                                                         |
| **Post-condizioni**| L'utente risulta correttamente abilitato alla partecipazione nel sistema di gamification.                                                                                                                                                                                                                              |

---

#### TestG_2 - Gestione Profilo
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                            |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di gestione e modifica del profilo utente.                                                                                                                                                                                         |
| **Pre-condizioni** | L'utente deve partecipare al sistema di gamification.                                                                                                                                                                                                  |
| **Azioni**         | 1. L'utente accede alla sezione "Profilo" all'interno della gamification.<br/> 2. Seleziona il pulsante relativo alla gestione del profilo.<br/> 3. Modifica i dati attraverso i menu appositi.<br/> 4. Il sistema applica le modifiche e reindirizza l'utente alla home.           |
| **Post-condizioni**| Il profilo utente viene aggiornato correttamente.                                                                                                                                                                                                      |

---

#### TestG_3 - Inserimento Commento/Recensione
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                            |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della funzionalità per l'inserimento di commenti o recensioni sui libri.                                                                                                                                                                      |
| **Pre-condizioni** | L'utente deve partecipare al sistema di gamification.                                                                                                                                                                                                  |
| **Azioni**         | 1. L'utente accede alla pagina del libro da recensire.<br/> 2. Seleziona il pulsante "Recensisci".<br/> 3. Inserisce il testo della recensione e clicca su "Invia".                                                                                                                                    |
| **Post-condizioni**| Il commento o la recensione viene aggiunto al sistema.                                                                                                                                                                                                 |
 
---

#### TestG_4 - Segnalazione Commento/Recensione
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                            |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della segnalazione di un commento o recensione inappropriata.                                                                                                                                                                                   |
| **Pre-condizioni** | L'utente ha già pubblicato un commento o una recensione; l'operazione viene eseguita da un bibliotecario.                                                                                                                                             |
| **Azioni**         | 1. Il bibliotecario individua il commento o la recensione da segnalare nella pagina del libro.<br/> 2. Seleziona il pulsante "Segnala".<br/> 3. Il sistema rimuove il contenuto e, se previsto, applica una penalizzazione sui punti dell'utente.                                                |
| **Post-condizioni**| Il commento o la recensione viene rimosso e vengono applicate eventuali penalizzazioni all'utente.                                                                                                                                                      |

---

#### TestG_5 - Riscatto Punti
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                               |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura per il riscatto dei punti accumulati per ottenere premi.                                                                                                                                                                          |
| **Pre-condizioni** | L'utente deve partecipare al sistema di gamification e avere un punteggio sufficiente.                                                                                                                                                                     |
| **Azioni**         | 1. L'utente accede alla sezione "Gamification".<br/> 2. Seleziona il pulsante "Riscatta Punti".<br/> 3. Sceglie il premio desiderato.<br/> 4. Il sistema elabora la richiesta, rilascia una ricevuta, consegna il premio e sottrae i punti corrispondenti. |
| **Post-condizioni**| Il premio viene riscattato e il punteggio dell'utente aggiornato.                                                                                                                                                                                           |

---

### Prestito Libri (PL)
- **PL_1**: Ricerca Libro Fisico e Richiesta di Prestito  
- **PL_2**: Restituzione Prestito Fisico  
- **PL_3**: Richiesta Allungamento Prestito Fisico  
- **PL_4**: Richiesta E-book

#### TestPL_1 - Ricerca Libro Fisico e Richiesta di Prestito
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                     |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di ricerca del libro fisico e della richiesta di prestito.                                                                                                                                                                                                 |
| **Pre-condizioni** | L'utente deve essere autenticato per completare la richiesta di prestito.                                                                                                                                                                                                         |
| **Azioni**         | 1. L'utente inserisce i termini di ricerca nella barra dedicata.<br/> 2. Il sistema visualizza una lista di almeno 50 libri corrispondenti ai criteri (ulteriori risultati sono accessibili cliccando per pagine successive).<br/> 3a. Se l'utente è autenticato, può inviare la richiesta di prestito e visualizzare la biblioteca per il ritiro.<br/> 3b. Se l'utente è un UtenteGuest, appare un messaggio che invita alla registrazione o all'autenticazione. |
| **Post-condizioni**| La richiesta di prestito viene registrata, oppure l'utente viene invitato a registrarsi per procedere.                                                                                                                                                                            |

---

#### TestPL_2 - Restituzione Prestito Fisico
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                          |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura per la restituzione di un libro fisico in prestito.                                                                                                                                                                                                           |
| **Pre-condizioni** | Esiste un prestito attivo per il libro.                                                                                                                                                                                                                                                 |
| **Azioni**         | 1. Il bibliotecario scannerizza il libro restituito.<br/> 2. Il sistema riceve una chiamata API che conferma la restituzione.<br/> 3. Il libro viene aggiornato come disponibile.                                                                                                    |
| **Post-condizioni**| Il libro viene reso disponibile per un nuovo prestito.                                                                                                                                                                                                                                   |

---

#### TestPL_3 - Richiesta Allungamento Prestito Fisico
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                           |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo per richiedere l'allungamento del periodo di prestito di un libro fisico.                                                                                                                                                                                        |
| **Pre-condizioni** | Esiste un prestito attivo per il libro.                                                                                                                                                                                                                                                  |
| **Azioni**         | 1. L'utente accede al proprio profilo e individua il prestito attivo.<br/> 2. Seleziona il pulsante "Allunga prestito".<br/> 3. Il sistema invia una richiesta all'ufficio di competenza.<br/> 4. L'utente viene informato via email dell'esito della richiesta.              |
| **Post-condizioni**| Viene inviata correttamente la richiesta di allungamento del prestito.                                                                                                                                                                                                                   |

---

#### TestPL_4 - Richiesta E-book
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                    |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura per la richiesta di prestito di un e-book.                                                                                                                                                                                                              |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                                 |
| **Azioni**         | 1. L'utente accede alla sezione degli e-book e ricerca il titolo desiderato.<br/> 2. Seleziona il pulsante "Prestito".<br/> 3. Accetta i termini e le condizioni proposti.<br/> 4. Il sistema concede l’accesso all’e-book in base ai termini della licenza.           |
| **Post-condizioni**| L'utente riceve l'accesso all’e-book.                                                                                                                                                                                                                                             |

---

### Prenotazione Spazi (PS)
- **PS_1**: Prenotazione di uno Spazio Comune  
- **PS_2**: Cancellazione di una Prenotazione  

#### TestPS_1 - Prenotazione di uno Spazio Comune
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di prenotazione di uno spazio comune presso una biblioteca.                                                                                                                                                                                          |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                             |
| **Azioni**         | 1. L'utente accede alla schermata delle prenotazioni per la biblioteca scelta.<br/> 2. Il sistema invia una mail con i dettagli della richiesta alla biblioteca.<br/> 3. In seguito alla risposta della biblioteca, il sistema comunica l'esito all'utente.             |
| **Post-condizioni**| L'utente riceve una notifica via email con l'esito della prenotazione.                                                                                                                                                                                                        |

---



#### TestPS_2 - Cancellazione di una Prenotazione
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo per la cancellazione di una prenotazione attiva.                                                                                                                                                                                                      |
| **Pre-condizioni** | Esiste una prenotazione attiva.                                                                                                                                                                                                                                               |
| **Azioni**         | 1. L'utente accede alla schermata delle prenotazioni nel proprio profilo e seleziona "Cancella" per la prenotazione desiderata.<br/> 2. Il sistema invia una mail di conferma della cancellazione alla biblioteca.                                                  |
| **Post-condizioni**| La prenotazione viene cancellata e l'utente riceve una conferma via email.                                                                                                                                                                                                   |

---



### Sezione Amministrativa (SA)
- **SA_1**: Caricamento Nuovi Libri  
- **SA_2**: Segnalazione Prestito Avvenuto Dal Vivo  
- **SA_3**: Segnalazione Notizie  
- **SA_4**: Gestione Pagina della Biblioteca

#### TestSA_1 - Caricamento Nuovi Libri
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di caricamento di nuovi libri nel sistema.                                                                                                                                                                                                            |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                             |
| **Azioni**         | 1. Il bibliotecario accede alla sezione amministrativa e seleziona il pulsante "Aggiungi un libro".<br/> 2. Scannerizza il codice del libro e inserisce i dati richiesti.<br/> 3. Il sistema aggiorna il catalogo rendendo il libro disponibile agli utenti.              |
| **Post-condizioni**| Il nuovo libro risulta presente nel catalogo della biblioteca e visibile sul portale.                                                                                                                                                                                         |

---

#### TestSA_2 - Segnalazione Prestito Avvenuto Dal Vivo
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica del processo di segnalazione di un prestito avvenuto dal vivo.                                                                                                                                                                                                      |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                             |
| **Azioni**         | 1. Il bibliotecario accede alla sezione amministrativa e seleziona l'opzione per segnalare un prestito avvenuto.<br/> 2. Scannerizza il codice del libro e inserisce i dati necessari.<br/> 3. Il sistema aggiorna lo stato del libro, segnalandolo come in prestito.        |
| **Post-condizioni**| Il libro viene aggiornato e non risulta più disponibile per nuove prenotazioni.                                                                                                                                                                                               |

---

#### TestSA_3 - Segnalazione Notizie
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura per la pubblicazione e aggiornamento delle notizie relative alla biblioteca.                                                                                                                                                                       |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                             |
| **Azioni**         | 1. Il bibliotecario accede alla sezione amministrativa e seleziona "Nuove notizie".<br/> 2. Compila il form per aggiungere, modificare o eliminare notizie.<br/> 3. Il sistema aggiorna la pagina della biblioteca con le nuove informazioni.                         |
| **Post-condizioni**| La sezione notizie viene aggiornata correttamente.                                                                                                                                                                                                                           |

---

#### TestSA_4 - Gestione Pagina della Biblioteca
| **Campo**          | **Dettaglio**                                                                                                                                                                                                                                                                |
|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Descrizione**    | Verifica della procedura per la gestione e la modifica della pagina della biblioteca.                                                                                                                                                                                       |
| **Pre-condizioni** | Nessuna pre-condizione specifica.                                                                                                                                                                                                                                             |
| **Azioni**         | 1. Il bibliotecario accede alla sezione amministrativa e seleziona l'opzione "Modifica tema".<br/> 2. Utilizza i menu dedicati per personalizzare la pagina.<br/> 3. Il sistema aggiorna la pagina della biblioteca in base alle modifiche apportate.                      |
| **Post-condizioni**| La pagina della biblioteca risulta aggiornata e riflette le modifiche effettuate.                                                                                                                                                                                            |

---
