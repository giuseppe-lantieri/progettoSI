
# Piano di Test del Progetto Biblioteche di Roma
## Scopo del documento
Questo documento descrive il piano di test svolto per la validazione delle funzionalità definite nel piano di _"progetto"_ e che sono elencate di seguito:
* Landing page
* Pagina personalizzata per biblioteca
* Gestione degli utenti
* Ricerca e prenotazione dei libri
* Ricerca e prenotazione di un posto in aula co-working/studio.
* Mappa interattiva

Ogni funzionalità con i relativi test è stata descritta nei paragrafi successivi






## Landing page
Il portale permetterà di accedere alle informazioni di ogni biblioteca, guidando l'utente attraverso le varie sezioni del sito.
## Pagina personalizzata per biblioteca
<!-- TODO trova nome decente -->
Ogni pagina avrà una sezione comune a tutte le biblioteche dove saranno specificate indirizzo, contatti, orari e servizi.

Use Case di riferimento
UC.1.1_AccessoLandingPage di una Biblioteca

| TestT.1 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.1_AccessoLandingPage | Verifica accesso  alla home page di una determinata biblioteca| AccessoLandingPage di una Biblioteca |
| Pre-condizioni | Azioni| Post-condizioni |
| Accesso ad internet| 1.l'utente accede alla homepage del portale 2.seleziona dalla lista dei municipi il municipio di interesse 3.Seleziona la biblioteca a cui vuole accedere| 1.La pagina cambia alla home page della biblioteca selezionata mostrando le sezione informativa comune a tutte le biblioteche  2.La pagina mostra anche una sezione di notizie, menu e link utili specifica per la biblioteca |


## Gestione degli utenti
Il portale permetterà di gestire vari tipi di utenti tramite ruoli distinti. Ad ogni ruolo corrisponderanno permessi differenti che influenzeranno la visione del portale.
L'utente amministratore potrà personalizzare la pagina della biblioteca di riferimento.
L'utente semplice potrà accedere tramite servizi di identificazione elettronica per poi cercare e prenotare libri e aule studio.

| TestT.2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.2_Gestione Utenti con Ruoli differenti | Verifica ruolo amministrativo| Accesso alle funzionalità di personalizzazione delle pagina della  Biblioteca |
| Pre-condizioni | Azioni| Post-condizioni |
| 1. Non esiste il nuovo utente amministrativo da creare.  2. Esiste un'utente admin del portale con tutti i permessi da amministratore del portale| 1.l'utente amministratore accede alla homepage del portale 2.L'utente crea l'utente amministratore di una biblioteca e assegna una password di default   3. L'utente amministratore della biblioteca accede al portale e cambia la password| 1.L'utente amministratore accede al portale dove saranno disponibili i menu di personalizzazione delle informazioni della biblioteca seguenti: 1.1 info di contatto 1.2 Notizie 1.3 Gestione Sale studio 1.4 Eventi 1.4 Aggiungi Sezione |

| TestT.3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.2_Gestione Utenti con Ruoli differenti | Verifica ruolo personale amministrativo| Accesso alle funzionalità di gestione della biblioteca |
| Pre-condizioni | Azioni| Post-condizioni |
|1.  Non esiste il nuovo utente amministratore biblioteca da creare. 2. Esiste un'utente admin del portale con tutti i permessi da amministratore del portale| 1.l'utente amministratore biblioteca accede alla homepage del portale 2.L'utente crea l'utente amministratore di una biblioteca e assegna una password di default 3.L'utente amministratore della biblioteca accede al portale e cambia la password| 1.L'utente amministratore della biblioteca accede al portale dove saranno disponibili i menu di personalizzazione delle informazioni della biblioteca seguenti: 1.1 Registra Utente 1.2 Gestisci Prenotazioni 1.3 Aggiungi/Cancella Libro 1.4 Gestisci Sala Studio

## Ricerca e prenotazione dei libri
Il portale guiderà l'utente alla ricerca del libro che, una volta selezionato permetterà di visionare tutte le caratteristiche e le biblioteche in cui è disponibile dando l'opzione di prenotarlo.

| TestT.4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.3_Ricerca  dei libri | Verifica funzionalità di ricerca libro| Accesso alle funzionalità di ricerca di un libro |
| Pre-condizioni | Azioni| Post-condizioni |
|1.  Il libro esiste ed è caricato nella biblioteca. | 1.l'utente della biblioteca accede alla homepage del portale 2.L'utente seleziona un libro | 1.L'utente della biblioteca visualizzerà le informazioni del libro|

| TestT.5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.3_Prenotazione dei libri | Verifica funzionalità di prenotazione libro| Accesso alle funzionalità di prenotazione di un libro con possibilità di prenotazione|
| Pre-condizioni | Azioni| Post-condizioni |
|1.  Il libro esiste ed è caricato nella biblioteca. 2.Il libro è disponibile nella biblioteca selezionata | 1.l'utente della biblioteca seleziona il libro desiderato 2.L'utente seleziona la biblioteca di interesse in cui il  libro è disponibile | 1.L'utente della biblioteca visualizzerà il pulsante di prenotazione. 2. L'utente cliccherà sul bottone prenota visualizzando il riepilogo della prenotazione|

## Ricerca e prenotazione di un posto in aula co-working/studio.
Il portale permetterà all'utente di visualizzare le biblioteche con aule studio libere negli orari selezionati dando l'opzione di prenotare un posto per il tempo stabilito.

| TestT.6 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.4_Ricerca Sala Studio | Verifica funzionalità ricerca posto in sala studio| Accesso alle funzionalità di ricerca di un un posto in sala studio con possibilità di prenotazione|
| Pre-condizioni | Azioni| Post-condizioni |
|1.  La sala studio esiste ed è caricata nella biblioteca. | 1.l'utente della biblioteca accede alla ricerca dei posti liberi  2.L'utente seleziona la biblioteca di interesse in cui il  posto è disponibile | 1.L'utente della biblioteca visualizzerà il pulsante di prenotazione. 2. L'utente cliccherà sul bottone prenota visualizzando il riepilogo della prenotazione|
## Mappa interattiva
Gli utenti avranno a disposizione una mappa interattiva che permetterà di esplorare e interagire con informazioni geografiche delle biblioteche, dando la possibilità di accedere alla scheda della biblioteca selezionata.

| TestT.7 | Scopo | Descrizione |
| :--- | :--- | :--- |
| UC.1.4_MappaInterattiva | Verifica funzionalità ricerca Biblioteche tramite localizzazione| Accesso alle funzionalità di ricerca di un biblioteca consultando la mappa interattiva che geo-localizza le biblioteche|
| Pre-condizioni | Azioni| Post-condizioni |
|1.  Accesso alla homepage. | 1.l'utente della biblioteca accede alla mappa nella homepage del portale  2.L'utente seleziona la zona  o il municipio di interesse | 1.L'utente della biblioteca visualizzerà le biblioteche disponibili nella zona o nel municipio selezionati. 2. L'utente cliccherà sull'icona delle biblioteca scelta accedendo alla sua Landing Page|


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
| -|- |-  |

| TestAU_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_2_Autenticazione_Utente_Sistema_Esterno | Autenticazione Utente Sistema Esterno| Verifica Autenticazione Utente tramite Sistema Esterno| |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestAU_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_3_Modifica Password sistema interno | Modifica Password sistema interno| Verifica Modifica Password sistema interno |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestAU_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_4_Login | Login| Verifica Login |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestAU_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| AU_5_Logout | Logout| Verifica Logout |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

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
| -|- |-  |

| TestT_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_2_Rinnovo Tesseramento| Rinnovo Tesseramento| Verifica Rinnovo Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestT_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_3_Cancellazione Tesseramento| Cancellazione Tesseramento| Verifica Cancellazione Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestT_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_4_Denuncia smarrimento Tesseramento| Denuncia smarrimento Tesseramento| Verifica Denuncia smarrimento Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestT_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_5_Denuncia furto Tesseramento| Denuncia furto Tesseramento| Verifica Denuncia furto Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

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
| -|- |-  |

| TestG_2 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_2_Gestione Profilo| Gestione Profilo| Verifica Gestione Profilo |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestG_3 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_3_Inserimento Commento/Recensione| Inserimento Commento/Recensione| Verifica Inserimento Commento/Recensione |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestG_4 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_4_Segnalazione Commento/Recensione| Segnalazione Commento/Recensione| Verifica Segnalazione Commento/Recensione |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

| TestG_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| G_5_Riscatto Punti| Riscatto Punti| Verifica Riscatto Punti |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |


### PrestitoLibri (PL):
- **PL_1**: Ricerca Libro fisico e richiesta di prestito
- **PL_2**: Restituzione Prestito fisico
- **PL_3**: Richiesta allungamento Prestito fisico
- **PL_4**: Richiesta e-book

| Test| Scopo | Descrizione |
| :--- | :--- | :--- |
| PL_1_Ricerca Libro fisico e richiesta di prestito| Ricerca Libro fisico e richiesta di prestito| Verifica Ricerca Libro fisico e richiesta di prestito |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

### PrenotazioneSpazio (PS):
- **PS_1**: Prenotazione di uno spazio comune
- **PS_2**: Richiesta allungamento di una prenotazione
- **PS_3**: Cancellazione di una richiesta
- **PS_4**: Segnalazione richiesta/comportamento errato

| TestT_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_5_Denuncia furto Tesseramento| Denuncia furto Tesseramento| Verifica Denuncia furto Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

### Sezione Amministrativa (SA):
- **SA_1**: Caricamento nuovi libri
- **SA_2**: Segnalazione prestito avvenuto dal vivo
- **SA_3**: Segnalazione notizie
- **SA_4**: Gestione pagina della biblioteca

| TestT_5 | Scopo | Descrizione |
| :--- | :--- | :--- |
| T_5_Denuncia furto Tesseramento| Denuncia furto Tesseramento| Verifica Denuncia furto Tesseramento |
| Pre-condizioni | Azioni| Post-condizioni |
| -|- |-  |

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

	

	


	

	
	


