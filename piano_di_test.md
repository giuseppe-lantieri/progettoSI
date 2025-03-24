
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

	

	


	

	
	


