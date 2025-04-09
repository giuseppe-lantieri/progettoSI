
# Piano di Test del Progetto Biblioteche di Roma
## Scopo del documento
Questo documento descrive il piano di test svolto per la validazione dei seguenti casi d'uso.

##Prerequisti Generali
- Presenza di una connessione internet
- Utenza di amministrazione esistente
- Archivio dei libri da prenotare già caricato nel sistema
- Utenza Bibliotecario esistente
- Servizio WiFi funzionante
- Funzione di localizzazione della posizione impostata sul browser


Elenco casi d'uso
### AutenticazioneUtenti (AU):
- **AU_1**: Autenticazione Utente Sistema Interno
- **AU_2**: Autenticazione Utente tramite Sistema Esterno
- **AU_3**: Modifica Password sistema interno
- **AU_4**: Login
- **AU_5**: Logout

| TestAU_1 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_1_Autenticazione_Utente_Sistema_Interno | Autenticazione Utente Sistema Interno| Verifica Autenticazione Utente Sistema Interno |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente registrato correttamente dal servizio|1. Si preme il pulsante per accedere <br/> 2. Si compila il form con email e password <br/>3a. Il sistema autentica l'utente <br/> &nbsp;&nbsp;&nbsp;&nbsp; 3b. Il sistema rigetta l'autenticazione dell'utente |UtenteGuest si trasforma in Utente o viene rigettato  |

| TestAU_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_2_Autenticazione_Utente_Sistema_Esterno | Autenticazione Utente Sistema Esterno| Un utente vuole effettuare l'accesso tramite servizio dello stato come CIE o SPID| 
| Pre-condizioni | Azioni| Post-condizioni |
| -|1. Si preme il pulsante corrispondente al servizio scelto <br/> 2. Si viene reindirizzati alla pagina del servizio <br/>3. Il sistema esterno certifica l'utente rilasciando le informazioni dell'utente <br/>4. Il sistema verifica la presenza dell'utente <br/>5. In base al risultato della verifica <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5a. Il sistema autentica l'utente <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5b. Il sistema genera un nuovo utente e lo accoglie |UtenteGuest si trasforma in Utente o viene rigettato |

| TestAU_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_3_Modifica Password sistema interno | Modifica Password sistema interno| Verifica Modifica Password sistema interno |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente pre registrato|1. Si preme il pulsante "ho dimenticato la password! <br/> 2. Si viene reindirizzati alla pagina con un form dove immettere email <br/>3. Il sistema invia una password temporanea alla mail dell'utente <br/>4. Il sistema forza la password temporanea nell'account <br/>5. Al login successivo l'utente dovrà settare una nuova password|UtenteGuest modifica la password di Utente  |

| TestAU_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_4_Login | Login| Verifica Login |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente mai registrato prima d'ora| 1. Si preme il pulsante Registrami <br/> 2. Si viene reindirizzati alla pagina con un form dove immettere email, dati anagrafici e viene scelta una password <br/>3. Il sistema salva le informazioni in modo sicuro nel database <br/>4. L'utente viene reindirizzato al login dove farà accesso tramite email e password| UtenteGuest diventa un nuovo Utente |

| TestAU_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_5_Logout | Logout| Verifica Logout |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente loggato |1. Si preme il pulsante Logout <br/> 2. Si viene reindirizzati alla pagina iniziale del sito, mentre il sistema invalida i cookie e la sessione|Utente diventa un nuovo UtenteGuest|


### Tesseramento (T):
- **T_1**: Nuovo Tesseramento
- **T_2**: Rinnovo Tesseramento
- **T_3**: Cancellazione Tesseramento
- **T_4**: Denuncia smarrimento Tesseramento
- **T_5**: Denuncia furto Tesseramento

| TestT_1 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_1_Nuovo Tesseramento| Nuovo Tesseramento| Verifica Nuovo Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente sprovvisto di tessera|1. Si preme il pulsante Nuovo tesseramento <br/> 2. SI viene reindirizzati su una nuova pagina contenente un form che richiede l'anagrafica e fa selezionare il tier della tessera <br/>3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. L'utente clicca sul bottone invia e riceve la ricevuta e l'indirizzo della biblioteca dove ritirare la tessera| Utente invia la sua richiesta di tessera|

| TestT_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_2_Rinnovo Tesseramento| Rinnovo Tesseramento| Verifica Rinnovo Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente provvisto di tessera|1. Si preme il pulsante Rinnovo tesseramento <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. L'utente clicca su invia e riceve  la ricevuta| Utente invia la sua richiesta di rinnovo|

| TestT_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_3_Cancellazione Tesseramento| Cancellazione Tesseramento| Verifica Cancellazione Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente provvisto di tessera| 	1. Si preme il pulsante Cancellazione tesseramento <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. L'utente clicca e riceve la ricevuta| Utente invia la sua richiesta di cancellazione|

| TestT_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_4_Denuncia smarrimento Tesseramento| Denuncia smarrimento Tesseramento| Verifica Denuncia smarrimento Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente provvisto di tessera|1. Si preme il pulsante Smarrimento tessera <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. L'utente clicca su invia e riceve la ricevuta|Utente denuncia lo smarrimento|

| TestT_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_5_Denuncia furto Tesseramento| Denuncia furto Tesseramento| Verifica Denuncia furto Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| Utente provvisto di tessera|	1. Si preme il pulsante Smarrimento tessera <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. L'utente allega la denuncia di furto effettuata all'ordine competente <br/> 4. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 5. L'utente clicca su invia e riceve la ricevuta| Utente denuncia il suo furto|

### Gamification (G):
- **G_1**: Partecipazione al sistema di gamification
- **G_2**: Gestione Profilo
- **G_3**: Inserimento Commento/Recensione
- **G_4**: Segnalazione Commento/Recensione
- **G_5**: Riscatto Punti

| TestG_1 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_1_Partecipazione al sistema di gamification| Partecipazione al sistema di gamification| Verifica Partecipazione al sistema di gamification |
| Pre-condizioni | Azioni| Post-condizioni |
| Essere un Utente | 	1. Si entra nella sezione gamification  <br/> 2. Si preme il pulsante "voglio partecipare al gioco" 3. L'utente legge il regolamento e accetta le condizioni <br/> 4. Il sistema segnala la partecipazione dell'utente garantendogli accesso alla sezione gamification del sito | Utente partecipa al sistema di gamification|

| TestG_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_2_Gestione Profilo| Gestione Profilo| Verifica Gestione Profilo |
| Pre-condizioni | Azioni| Post-condizioni |
| Essere un Utente che partecipa alla gamification | 	1. Si entra nella sezione gamification  <br/> 2. Si preme il pulsante "Profilo" 3. L'utente può modificare quello che gli interessa tramite i menu appositi<br/> 4. Il sistema segnala le modifiche e riporta l'utente nella home |Viene modificata la pagina riferita all'utente |


| TestG_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_3_Inserimento Commento/Recensione| Inserimento Commento/Recensione| Verifica Inserimento Commento/Recensione |
| Pre-condizioni | Azioni| Post-condizioni |
| Essere un Utente che partecipa alla gamification|	1. Si entra nel libro da recensire  <br/> 2. Si preme il pulsante "Recensisci" 3. L'utente scrive la recensione e clicca su invia| Viene aggiunta una recensione/commento |

| TestG_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_4_Segnalazione Commento/Recensione| Segnalazione Commento/Recensione| Verifica Segnalazione Commento/Recensione |
| Pre-condizioni | Azioni| Post-condizioni |
| Essere un bibliotecario| 	1. Si individua la recensione/commento da eliminare nella pagina del libro <br/> 2. Si preme il pulsante "Segnala" <br/> 3. Il sistema rimuove la recensione e rimuove punti all'utente|Viene rimossa una recensione/commento |


| TestG_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_5_Riscatto Punti| Riscatto Punti| Verifica Riscatto Punti |
| Pre-condizioni | Azioni| Post-condizioni |
| Essere un Utente che partecipa alla gamification| 	1. Si entra nella sezione Gamification <br/> 2. Si preme il pulsante "riscatta punti" <br/> 3. Si seleziona il premio preferito 4. Il sistema rilascia una ricevuta, il premio e toglie i punti consumati| Viene riscattato un premio e vengono rimossi i punti |


### PrestitoLibri (PL):
- **PL_1**: Ricerca Libro fisico e richiesta di prestito
- **PL_2**: Restituzione Prestito fisico
- **PL_3**: Richiesta allungamento Prestito fisico
- **PL_4**: Richiesta e-book

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PL_1_Ricerca Libro fisico e richiesta di prestito| Ricerca Libro fisico e richiesta di prestito| Verifica Ricerca Libro fisico e richiesta di prestito |
| Pre-condizioni | Azioni| Post-condizioni |
| Per terminare la richiesta di prestito bisogna essere un Utente|1. L'attore cerca nella barra di ricerca il libro o i tag che gli interessano <br/> 2. Il sistema presenta una lista di almeno 50 libri che rappresentano a pieno la ricerca fatta, i risultati superiori ai 50 verranno presentati cliccando sulla pagina seguente <br/> 3. Se l'utente sceglie una proposta dalla libreria in base al suo ruolo avremo diverse situazioni: <br/> &nbsp;&nbsp;&nbsp;&nbsp; 3a. Utente: Il sistema darà la possibilità di mandare la richiesta di prestito e indicherà a quale biblioteca potrà essere ritirato <br/>&nbsp;&nbsp;&nbsp;&nbsp; 3b. UtenteGuest: Il sistema farà apparire un banner che avvertirà l'attore che senza la registrazione o l'autenticazione non sarà possibile continuare, mostrando a schermo le possibili soluzioni|Viene prenotato un libro |

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PL_2_Restituzione Prestito fisico| Restituzione Prestito fisico| Verifica Restituzione Prestito fisico |
| Pre-condizioni | Azioni| Post-condizioni |
| Un prestito attivo|1. Il bibliotecario scannerizza il libro che gli viene restituito <br/> 2. Il sistema riceve una chiamata API che comunica la restituzione <br/> 3. Il libro ritorna attivo nel sistema| Il libro viene reso disponibile a un nuovo prestito|

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PL_3_Richiesta allungamento Prestito fisico| Richiesta allungamento Prestito fisico| Verifica Richiesta allungamento Prestito fisico |
| Pre-condizioni | Azioni| Post-condizioni |
| Un prestito attivo| 	1. L'utente va sul suo profilo e individua il prestito attivo e preme il pulsante "allunga prestito" <br/> 2. Il sistema invia una richiesta all'ufficio di competenza  <br/> 3. Il sistema informerà tramite mail con il risultato della richiesta| Viene inviato una richiesta di allungamento|

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PL_4_Richiesta e-book| Richiesta e-book| Verifica Richiesta e-book |
| Pre-condizioni | Azioni| Post-condizioni |
| -| 1. L'utente raggiunge la schermata degli ebook e cerca fra quelli presenti quello che gli interessa <br/> 2. Preme il pulsante di Prestito <br/> 3. Accetta i termini e le condizioni <br/> 4. In base ai termini il sistema toglie la concessione del prestito dell'ebook all'utente | L'utente riceve un ebook|


### PrenotazioneSpazio (PS):
- **PS_1**: Prenotazione di uno spazio comune
- **PS_2**: Richiesta allungamento di una prenotazione
- **PS_3**: Cancellazione di una richiesta
- **PS_4**: Segnalazione richiesta/comportamento errato

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PS_1_Prenotazione di uno spazio comune| Prenotazione di uno spazio comune| Verifica Prenotazione di uno spazio comune |
| Pre-condizioni | Azioni| Post-condizioni |
| - | 	1. L'utente raggiunge la schermata delle prenotazioni sulla biblioteca scelta <br/> 2. Il sistema invia una mail con i dettagli della richiesta alla mail della biblioteca <br/> 3. In seguito alla risposta della biblioteca, il sistema genera una risposta all'utente | L'utente riceve una mail con il risultato della prenotazione|


| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PS_2_Richiesta allungamento di una prenotazione| Richiesta allungamento di una prenotazione| Verifica Richiesta allungamento di una prenotazione |
| Pre-condizioni | Azioni| Post-condizioni |
| - | 1. L'utente raggiunge la schermata delle prenotazioni sulla biblioteca scelta <br/> 2. Il sistema invia una mail con i dettagli della richiesta alla mail della biblioteca <br/> 3. In seguito alla risposta della biblioteca, il sistema genera una risposta all'utente | L'utente riceve una mail con il risultato della prenotazione|


| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PS_3_Cancellazione di una richiesta| Cancellazione di una richiesta| Verifica Cancellazione di una richiesta |
| Pre-condizioni | Azioni| Post-condizioni |
|Prenotazione attiva | 	1. L'utente raggiunge la schermata delle prenotazioni sul suo profilo e preme cancella sulla prenotazione scelta <br/> 2. Il sistema invia una mail che comunica la cancellazione della richiesta alla biblioteca | L'utente cancella la prenotazione|


| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PS_4_Segnalazione richiesta/comportamento errato| Segnalazione richiesta/comportamento errato| Verifica Segnalazione richiesta/comportamento errato |
| Pre-condizioni | Azioni| Post-condizioni |
| Prenotazione attiva |1. Il bibliotecario segnala dalla lista delle prenotazioni quella problematica <br/> 2. L'utente se presente tra quelli della gamification viene ammonito sui punti acquisiti | Un utente viene ammonito ai punti della gamification|

### Sezione Amministrativa (SA):
- **SA_1**: Caricamento nuovi libri
- **SA_2**: Segnalazione prestito avvenuto dal vivo
- **SA_3**: Segnalazione notizie
- **SA_4**: Gestione pagina della biblioteca

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| SA_1_Caricamento nuovi libri| Caricamento nuovi libri| Verifica Caricamento nuovi libri |
| Pre-condizioni | Azioni| Post-condizioni |
| -| 	1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante aggiungi un libro <br/> 2. Il bibliotecario scannerizza il codice del libro, inserisce i vari dati  <br/> 3. Il sistema propaga le informazioni rendendo disponibile il libro agli utenti | Un nuovo libro è presente nella lista della biblioteca e nel portale|

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| SA_2_Segnalazione prestito avvenuto dal vivo| Segnalazione prestito avvenuto dal vivo| Verifica Segnalazione prestito avvenuto dal vivo |
| Pre-condizioni | Azioni| Post-condizioni |
| -| 1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante aggiungi un libro <br/> 2. Il bibliotecario scannerizza il codice del libro, inserisce i vari dati  <br/> 3. Il sistema propaga le informazioni  rendendo non più disponibile il libro agli utenti| Un libro viene segnato come in prestito|

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| SA_3_Segnalazione notizie| Segnalazione notizie| Verifica Segnalazione notizie |
| Pre-condizioni | Azioni| Post-condizioni |
| -| 1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante nuove notizie <br/> 2. Compila un form dove può aggiungere nuove notizie, modificarle o eliminare quelle già presenti  <br/> 3. Il sistema propaga le informazioni aggiornando la pagina della biblioteca corrispondente| Viene aggiornata la sezione notizie della pagina della biblioteca|

| Test | Scopo | Descrizione |
| :--- | :--- | :--- |
| SA_4_Gestione pagina della biblioteca| Gestione pagina della biblioteca| Verifica Gestione pagina della biblioteca |
| Pre-condizioni | Azioni| Post-condizioni |
| -| 1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante modifica tema <br/> 2. Utilizzando i menu appositi modifica per quanto possibile la pagina della biblioteca  <br/> 3. Il sistema propaga le informazioni aggiornando la pagina della biblioteca corrispondente| Viene aggiornata la pagina della biblioteca|

