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
- **AU_4**: Login
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
- **PS_2**: Richiesta allungamento di una prenotazione
- **PS_3**: Cancellazione di una richiesta
- **PS_4**: Segnalazione richiesta/comportamento errato

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

<!-- XXX Per evitare Il fatto che venisse una merda ho usato br e lo spazio in html così viene renderizzato meglio, se qualcuno trova una migliore soluzione tutto orecchie -->