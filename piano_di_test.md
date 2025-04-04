
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

	

	


	

	
	


