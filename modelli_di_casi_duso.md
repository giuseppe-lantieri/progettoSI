# Biblioteche di Roma
### Modelli di Caso d'Uso

## Introduzione 
<!-- TODO Spiegare cosa è il file -->

## Attori
Procederemo ad elencare e spiegare i possibili attori, che interagiranno con il portale.
Ogni attore verrà descritto con i seguenti parametri: 
 - **ID**: un identifico unico con cui ci riferiremo all'attore 
 - **Nome**: un nome atto a descrivere correttamente l'attore, in modo che sia comprensibile anche ai non tecnici
 - **Genitore**: indica l'attore da cui ha avuto origine  
 - **Tipo**: Distingue la tipologia di attore in base alle sue possibili interazioni
 - **Descrizione**: Una breve descrizione dell'attore in modo che possa essere chiara la sua funzione

 <!-- XXX Struttura tabella  
	|||
	|--|--|
	|ID| |
	|Nome| |
	|Genitore| |
	|Tipo| |
	|Descrizione| | 
  -->
|||
|--|--|
|ID| 1|
|Nome| UtenteGuest|
|Genitore| -|
|Tipo| Secondario|
|Descrizione| Un utente che accede senza effettuare l'accesso, avrà operazioni limitate|

|||
|--|--|
|ID| 2|
|Nome| Utente|
|Genitore| UtenteGuest|
|Tipo| Primario|
|Descrizione| Un utente che decide di effettuare il login e perciò sblocca le possibili operazioni aggiuntive|

|||
|--|--|
|ID| 3|
|Nome| Bibliotecario|
|Genitore| -|
|Tipo| Primario|
|Descrizione| Un dipendente della biblioteca con un particolare livello di permessi che gli permette di accedere alla sezione amministrativa del sito|

|||
|--|--|
|ID| 4|
|Nome| Servizio Esterno|
|Genitore| -|
|Tipo| Secondario|
|Descrizione| Un servizio esterno che accede al portale tramite il servizio API apposito|

## Casi D'uso

I casi d'uso verranno registrati ed elencati. Ogni caso d'uso verrà raggruppato in macro gruppi, chiamati scenari. 
La nomenclatura adottata sfrutterà la seguente metodologia:
 - **InizialiDelloScenario**_*NumeroIdentifico*

### AutenticazioneUtenti (AU):
- **AU_1**: Autenticazione Utente Sistema Interno
- **AU_2**: Autenticazione Utente tramite Sistema Esterno
- **AU_3**: Modifica Password sistema interno
- **AU_4**: Registrazione
- **AU_5**: Logout

### Tesseramento (T):
- **T_1**: Nuovo Tesseramento
- **T_2**: Rinnovo Tesseramento
- **T_3**: Cancellazione Tesseramento
- **T_4**: Denuncia smarrimento Tesseramento
- **T_5**: Denuncia furto Tesseramento

### Gamification (G):
- **G_1**: Partecipazione al sistema di gamification
- **G_2**: Gestione Profilo
- **G_3**: Inserimento Commento/Recensione
- **G_4**: Segnalazione Commento/Recensione
- **G_5**: Riscatto Punti

### PrestitoLibri (PL):
- **PL_1**: Ricerca Libro fisico e richiesta di prestito
- **PL_2**: Restituzione Prestito fisico
- **PL_3**: Richiesta allungamento Prestito fisico
- **PL_4**: Richiesta e-book

### PrenotazioneSpazio (PS):
- **PS_1**: Prenotazione di uno spazio comune
- **PS_2**: Cancellazione di una richiesta
- **PS_3**: Segnalazione richiesta/comportamento errato

### Sezione Amministrativa (SA):
- **SA_1**: Caricamento nuovi libri
- **SA_2**: Segnalazione prestito avvenuto dal vivo
- **SA_3**: Segnalazione notizie
- **SA_4**: Gestione pagina della biblioteca

## Tabelle Descrittive casi d'uso
Le seguenti tabelle descrittive, descriveranno i casi d'uso utilizzando il seguente schema:
- **ID**: un id che rappresenta il caso d'uso 
- **Nome**: Nome del caso d'uso
- **Priorità**: Un valore compreso tra 1 e 10 che esprime il rischio e il caso d'uso in se
- **Attori**: Attori coinvolti 
- **Descrizione**: Breve descrizione del caso d'uso
- **Condizioni**: Condizioni precedenti del sistema
- **Risultato**: Il sistema dopo che il caso d'uso è avvenuto
- **Flusso**: Descrizione delle interazioni dell'attore con il sistema


 <!-- XXX Struttura tabella  
	|||
	|--|--|
	|ID| |
	|Nome| |
	|Priorità| |
	|Attori| |
	|Descrizione| |
	|Condizioni| |
	|Risultato| |
	|Flusso| |
  -->

|||
|--|--|
|ID| AU_1|
|Nome| Autenticazione Utente Sistema Interno|
|Priorità| 10|
|Attori| UtenteGuest, Utente|
|Descrizione| Un utente vuole effettuare l'accesso tramite email e password con cui si è registrato precedentemente|
|Condizioni| Utente registrato correttamente dal servizio|
|Risultato| UtenteGuest si trasforma in Utente o viene rigettato|
|Flusso | 	1. Si preme il pulsante per accedere <br/> 2. Si compila il form con email e password <br/>3. Il sistema verifica email e password <br/>4. Il sistema verifica i dati immessi <br/>5. In base al risultato della verifica <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5a. Il sistema autentica l'utente <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5b. Il sistema rigetta l'autenticazione dell'utente|

|||
|--|--|
|ID| AU_2|
|Nome| Autenticazione Utente Tramite Sistema Esterno|
|Priorità| 10|
|Attori| UtenteGuest, Utente, Servizio esterno|
|Descrizione| Un utente vuole effettuare l'accesso tramite servizio dello stato come CIE o SPID|
|Condizioni| -|
|Risultato| UtenteGuest si trasforma in Utente o viene rigettato|
|Flusso | 	1. Si preme il pulsante corrispondente al servizio scelto <br/> 2. Si viene reindirizzati alla pagina del servizio <br/>3. Il sistema esterno certifica l'utente rilasciando le informazioni dell'utente <br/>4. Il sistema verifica la presenza dell'utente <br/>5. In base al risultato della verifica <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5a. Il sistema autentica l'utente <br/> &nbsp;&nbsp;&nbsp;&nbsp; 5b. Il sistema genera un nuovo utente e lo accoglie|


|||
|--|--|
|ID| AU_3|
|Nome| Modifica Password sistema interno|
|Priorità| 10|
|Attori| UtenteGuest|
|Descrizione| Un utente vuole cambiare la password |
|Condizioni| Utente pre registrato|
|Risultato| UtenteGuest modifica la password di Utente|
|Flusso | 	1. Si preme il pulsante "ho dimenticato la password! <br/> 2. Si viene reindirizzati alla pagina con un form dove immettere email <br/>3. Il sistema invia una password temporanea alla mail dell'utente <br/>4. Il sistema forza la password temporanea nell'account <br/>5. Al login successivo l'utente dovrà settare una nuova password|

|||
|--|--|
|ID| AU_4|
|Nome| Registrazione|
|Priorità| 10|
|Attori| UtenteGuest|
|Descrizione| Un utente vuole registrarsi tramite il servizio interno |
|Condizioni| Utente mai registrato prima d'ora|
|Risultato| UtenteGuest diventa un nuovo Utente|
|Flusso | 	1. Si preme il pulsante Registrami <br/> 2. Si viene reindirizzati alla pagina con un form dove immettere email, dati anagrafici e viene scelta una password <br/>3. Il sistema salva le informazioni in modo sicuro nel database <br/>4. L'utente viene reindirizzato al login dove farà accesso tramite email e password|


|||
|--|--|
|ID| AU_5|
|Nome| Logout|
|Priorità| 10|
|Attori| Utente|
|Descrizione| Un utente vuole chiudere la sua sessione dati |
|Condizioni| Utente |
|Risultato| Utente diventa un nuovo UtenteGuest|
|Flusso | 	1. Si preme il pulsante Logout <br/> 2. Si viene reindirizzati alla pagina iniziale del sito, mentre il sistema invalida i cookie e la sessione|

|||
|--|--|
|ID| T_1|
|Nome|  Nuovo Tesseramento|
|Priorità| 8|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere la sua tessera |
|Condizioni| Utente sprovvisto di tessera|
|Risultato| Utente invia la sua richiesta di tessera|
|Flusso | 	1. Si preme il pulsante Nuovo tesseramento <br/> 2. SI viene reindirizzati su una nuova pagina contenente un form che richiede l'anagrafica e fa selezionare il tier della tessera <br/>3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. Il sistema inoltra la richiesta di tesseramento all'ufficio competente e restituisce all'utente la ricevuta e l'indirizzo della biblioteca dove ritirare la tessera|
 
 
|||
|--|--|
|ID| T_2|
|Nome|  Rinnovo Tesseramento|
|Priorità| 5|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere il rinnovo della tessera |
|Condizioni| Utente provvisto di tessera|
|Risultato| Utente invia la sua richiesta di rinnovo|
|Flusso | 	1. Si preme il pulsante Rinnovo tesseramento <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. Il sistema inoltra la richiesta di rinnovo all'ufficio competente e restituisce all'utente la ricevuta|
 
|||
|--|--|
|ID| T_3|
|Nome| Cancellazione Tesseramento|
|Priorità| 7|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere la cancellazione della tessera |
|Condizioni| Utente provvisto di tessera|
|Risultato| Utente invia la sua richiesta di cancellazione|
|Flusso | 	1. Si preme il pulsante Cancellazione tesseramento <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. Il sistema inoltra la richiesta di cancellazione all'ufficio competente e restituisce all'utente la ricevuta|
 
|||
|--|--|
|ID| T_4|
|Nome| Denuncia smarrimento Tesseramento|
|Priorità| 8|
|Attori| Utente|
|Descrizione| Un utente vuole denunciare lo smarrimento della tessera |
|Condizioni| Utente provvisto di tessera|
|Risultato| Utente denuncia lo smarrimento|
|Flusso | 	1. Si preme il pulsante Smarrimento tessera <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 4. Il sistema inoltra la richiesta di smarrimento all'ufficio competente e restituisce all'utente la ricevuta|

|||
|--|--|
|ID| T_5|
|Nome| Denuncia furto Tesseramento|
|Priorità| 8|
|Attori| Utente|
|Descrizione| Un utente vuole denunciare il furto della tessera |
|Condizioni| Utente provvisto di tessera|
|Risultato| Utente denuncia il suo furto|
|Flusso | 	1. Si preme il pulsante Smarrimento tessera <br/> 2. Si viene reindirizzati su una nuova pagina contenente un form che richiede il codice della vecchia tessera <br/> 3. L'utente allega la denuncia di furto effettuata all'ordine competente <br/> 4. Il sistema alla sottoscrizione del form controlla tutti i vari campi segnalando all'utente la presenza di errori <br/> 5. Il sistema inoltra la richiesta di smarrimento all'ufficio competente e restituisce all'utente la ricevuta|

|||
|--|--|
|ID| G_1|
|Nome| Partecipazione al sistema di gamification|
|Priorità| 3|
|Attori| Utente|
|Descrizione| Un utente vuole partecipare alla gamification del sito |
|Condizioni| Essere un Utente |
|Risultato| Utente partecipa al sistema di gamification|
|Flusso | 	1. Si entra nella sezione gamification  <br/> 2. Si preme il pulsante "voglio partecipare al gioco" 3. L'utente legge il regolamento e accetta le condizioni <br/> 4. Il sistema segnala la partecipazione dell'utente garantendogli accesso alla sezione gamification del sito |

|||
|--|--|
|ID| G_2|
|Nome| Gestione Profilo|
|Priorità| 3|
|Attori| Utente|
|Descrizione| Un utente vuole personalizzare come appare il suo profilo |
|Condizioni| Essere un Utente che partecipa alla gamification |
|Risultato| Viene modificata la pagina riferita all'utente |
|Flusso | 	1. Si entra nella sezione gamification  <br/> 2. Si preme il pulsante "Profilo" 3. L'utente può modificare quello che gli interessa tramite i menu appositi<br/> 4. Il sistema segnala le modifiche e riporta l'utente nella home |

|||
|--|--|
|ID| G_3|
|Nome|Inserimento Commento/Recensione|
|Priorità| 3|
|Attori| Utente|
|Descrizione| Un utente vuole lasciare una recensione/commento |
|Condizioni| Essere un Utente che partecipa alla gamification|
|Risultato| Viene aggiunta una recensione/commento |
|Flusso | 	1. Si entra nel libro da recensire  <br/> 2. Si preme il pulsante "Recensisci" 3. L'utente scrive la recensione|

|||
|--|--|
|ID| G_4|
|Nome| Segnalazione Commento/Recensione|
|Priorità| 3|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole segnalare un commento/recensione |
|Condizioni| Essere un bibliotecario|
|Risultato| Viene rimossa una recensione/commento |
|Flusso | 	1. Si individua la recensione/commento da eliminare nella pagina del libro <br/> 2. Si preme il pulsante "Segnala" <br/> 3. Il sistema rimuove la recensione e rimuove punti all'utente|

|||
|--|--|
|ID| G_5|
|Nome| Riscatto Punti|
|Priorità| 1|
|Attori| Utente|
|Descrizione| Un utente vuole riscattare i punti|
|Condizioni| Essere un Utente che partecipa alla gamification|
|Risultato| Viene riscattato un premio e vengono rimossi i punti |
|Flusso | 	1. Si entra nella sezione Gamification <br/> 2. Si preme il pulsante "riscatta punti" <br/> 3. Si seleziona il premio preferito 4. Il sistema rilascia una ricevuta, il premio e toglie i punti consumati|

|||
|--|--|
|ID| PL_1|
|Nome| Ricerca Libro fisico e richiesta di prestito|
|Priorità| 9|
|Attori| UtenteGuest, Utente|
|Descrizione| Un qualsiasi tipo di utente vuole richiedere un libro|
|Condizioni| Per terminare la richiesta di prestito bisogna essere un Utente|
|Risultato| Viene prenotato un libro |
|Flusso | 	1. L'attore cerca nella barra di ricerca il libro o i tag che gli interessano <br/> 2. Il sistema presenta una lista di almeno 50 libri che rappresentano a pieno la ricerca fatta, i risultati superiori ai 50 verranno presentati solo su richiesta <br/> 3. Se l'attore sceglie una proposta dalla libra in base al suo ruolo avremo diverse situazioni: <br/> &nbsp;&nbsp;&nbsp;&nbsp; 3a. Utente: Il sistema darà la possibilità di mandare la richiesta di prestito e indicherà a quale biblioteca potrà essere ritirato <br/>&nbsp;&nbsp;&nbsp;&nbsp; 3b. UtenteGuest: Il sistema farà apparire un banner che avvertirà l'attore che senza la registrazione o l'autenticazione non sarà possibile continuare, mostrando a schermo le possibili soluzioni|

|||
|--|--|
|ID| PL_2|
|Nome|Restituzione Prestito fisico|
|Priorità| 9|
|Attori| Bibliotecario|
|Descrizione| Un Bibliotecario deve comunicare la chiusura di un prestito|
|Condizioni| Un prestito attivo|
|Risultato| Il libro viene reso disponibile a un nuovo prestito|
|Flusso | 	1. Il bibliotecario scannerizza il libro che gli viene restituito <br/> 2. Il sistema riceve una chiamata API che comunica la restituzione <br/> 3. Il libro ritorna attivo nel sistema|

|||
|--|--|
|ID| PL_3|
|Nome| Richiesta allungamento Prestito fisico|
|Priorità| 6|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere l'allungamento di un prestito|
|Condizioni| Un prestito attivo|
|Risultato| Viene inviato una richiesta di allungamento|
|Flusso | 	1. L'utente va sul suo profilo e individua il prestito attivo e preme il pulsante "allunga prestito" <br/> 2. Il sistema invia una richiesta all'ufficio di competenza  <br/> 3. Il sistema informerà tramite mail con il risultato della richiesta|

|||
|--|--|
|ID| PL_4|
|Nome| Richiesta e-book|
|Priorità| 4|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere un ebook|
|Condizioni| -|
|Risultato| L'utente riceve un ebook|
|Flusso | 	1. L'utente raggiunge la schermata degli ebook e cerca fra quelli presenti quello che gli interessa <br/> 2. Preme il pulsante di Prestito <br/> 3. Accetta i termini e le condizioni <br/> 4. In base ai termini il sistema toglie la concessione del prestito dell'ebook all'utente |

|||
|--|--|
|ID| PS_1|
|Nome| Prenotazione di uno spazio comune|
|Priorità| 3|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere uno spazio|
|Condizioni| - |
|Risultato| L'utente riceve una mail con il risultato della prenotazione|
|Flusso | 	1. L'utente raggiunge la schermata delle prenotazioni sulla biblioteca scelta <br/> 2. Il sistema invia una mail con i dettagli della richiesta alla mail della biblioteca <br/> 3. In seguito alla risposta della biblioteca, il sistema genera una risposta all'utente |


|||
|--|--|
|ID| PS_2|
|Nome| Prenotazione di uno spazio comune|
|Priorità| 3|
|Attori| Utente|
|Descrizione| Un utente vuole chiedere uno spazio|
|Condizioni| - |
|Risultato| L'utente riceve una mail con il risultato della prenotazione|
|Flusso | 	1. L'utente raggiunge la schermata delle prenotazioni sulla biblioteca scelta <br/> 2. Il sistema invia una mail con i dettagli della richiesta alla mail della biblioteca <br/> 3. In seguito alla risposta della biblioteca, il sistema genera una risposta all'utente |

|||
|--|--|
|ID| PS_2|
|Nome| Cancellazione di una richiesta|
|Priorità| 2|
|Attori| Utente|
|Descrizione| Un utente vuole cancellare una richiesta|
|Condizioni| Prenotazione attiva |
|Risultato| L'utente cancella la prenotazione|
|Flusso | 	1. L'utente raggiunge la schermata delle prenotazioni sul suo profilo e preme cancella sulla prenotazione scelta <br/> 2. Il sistema invia una mail che comunica la cancellazione della richiesta alla biblioteca |

|||
|--|--|
|ID| PS_3|
|Nome| Segnalazione richiesta/comportamento errato|
|Priorità| 3|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole segnalare una richiesta|
|Condizioni| Prenotazione attiva |
|Risultato| Un utente viene ammonito ai punti della gamification|
|Flusso | 	1. Il bibliotecario segnala dalla lista delle prenotazioni quella problematica <br/> 2. L'utente se presente tra quelli della gamification viene ammonito sui punti acquisiti |

|||
|--|--|
|ID| SA_1|
|Nome| Caricamento nuovi libri|
|Priorità| 8|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole caricare un nuovo libro|
|Condizioni| -|
|Risultato| Un nuovo libro è presente nella lista della biblioteca e nel portale|
|Flusso | 	1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante aggiungi un libro <br/> 2. Il bibliotecario scannerizza il codice del libro, inserisce i vari dati  <br/> 3. Il sistema propaga le informazioni rendendo disponibile il libro agli utenti |

|||
|--|--|
|ID| SA_2|
|Nome| Segnalazione prestito avvenuto dal vivo|
|Priorità| 8|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole segnalare un nuovo prestito|
|Condizioni| -|
|Risultato| Un libro viene segnato come in prestito|
|Flusso | 	1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante aggiungi un libro <br/> 2. Il bibliotecario scannerizza il codice del libro, inserisce i vari dati  <br/> 3. Il sistema propaga le informazioni  rendendo non più disponibile il libro agli utenti|

|||
|--|--|
|ID| SA_3|
|Nome| Segnalazione notizie|
|Priorità| 8|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole segnalare notizie riguardo la sua biblioteca|
|Condizioni| -|
|Risultato| Viene aggiornata la sezione notizie della pagina della biblioteca|
|Flusso | 	1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante nuove notizie <br/> 2. Compila un form dove può aggiungere nuove notizie, modificarle o eliminare quelle già presenti  <br/> 3. Il sistema propaga le informazioni aggiornando la pagina della biblioteca corrispondente|

|||
|--|--|
|ID| SA_4|
|Nome| Gestione pagina della biblioteca|
|Priorità| 6|
|Attori| Bibliotecario|
|Descrizione| Un bibliotecario vuole modificare l'aspetto della biblioteca|
|Condizioni| -|
|Risultato| Viene aggiornata la pagina della biblioteca|
|Flusso | 	1. Il bibliotecario raggiunge la sezione amministrativa e preme il pulsante modifica tema <br/> 2. Utilizzando i menu appositi modifica per quanto possibile la pagina della biblioteca  <br/> 3. Il sistema propaga le informazioni aggiornando la pagina della biblioteca corrispondente|
<!-- XXX Per evitare Il fatto che venisse una merda ho usato br e lo spazio in html così viene renderizzato meglio, se qualcuno trova una migliore soluzione tutto orecchie -->