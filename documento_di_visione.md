# Biblioteche di Roma
### Documento di visione
## Introduzione
Il comune di Roma vuole creare un nuovo portale online per il proprio sistema bibliotecario. 
Il portale deve dare la possibilità di accedere ai servizi offerti dalle biblioteche in maniera semplice e digitale. 
L'obbiettivo, perciò è riuscire a creare un semplice metodo per gli utenti di usufruire dei seguenti servizi:
- Prenotazione Libri
- Prestito Libri (Fisico e EBook)
- Prenotazione Posto (ove possibile)
- Servizio Wifi
- Servizio Tesseramento


Oltre a ciò il portale dovrà essere in grado di:
- Segnalare notizie riguardanti le singole biblioteche
- Offrire indicazioni chiare e veloci sulla posizione
- Aggregare i database
- Permettere i login tramite i servizi di stato
<!-- TODO Non ho idea se lasciarlo
- Aderire al servizio Open Data 
-->
- Gamification 

## Prenotazione Libri 
Il portale deve permettere ai vari utenti (che hanno fatto o meno l'accesso) di verificare la presenza dei libri, indicando se sono fisici o ebook, nel caso dovrà aggiungere le informazioni riguardanti la libreria che lo possiede, la posizione o nel caso fosse preso mettere in risalto i giorni rimanenti prima che finisca il prestito.

## Prestito Libri
Il prestito libri differisce in base al formato del libro:
- Fisico: 
	
	Il libro fisico non potrà per ovvie ragione essere preso direttamente online, il portale per permettere il servizio dovrà:
	
	1) Segnalare la presa in carico al database
	2) Creare una ricevuta apposita da consegnare all'utente
	3) Permettere al bibliotecario di convalidare l'autenticità della ricevuta
	4) Impedire agli altri utenti di prenotare all'ora volta il libro

- Ebook: 
	Il libro digitale dovrà essere gestito interamente dal portale, per assicurare che i termini e le licenze dell'ebook non vengano violati deve limitare le interazione dell'utente con esso, ma permetterne comunque una lettura agevole e senza impacci.

## Prenotazione Posto

Alcune biblioteche offrono tavoli e stanze, adibite al co-working e allo studio. 
Il portale dovrà:
1) Segnalare se la biblioteca scelta ha un posto disponibile
2) Gestire la prenotazione anche in caso di concorrenza
3) Permettere la verifica di quest'ultima da parte di un bibliotecario
4) Segnalare al bibliotecario la fine di una prenotazione in modo che esso possa controllare
5) Permettere all'utente di estendere la propria prenotazione

## Servizio Wifi 

Il portale deve offrire la possibilità di entrare all'interno della connessione protetta offerta dal comune di Roma. Il servizio è accessibile solo alle persone che hanno aderito a un certo livello di tesseramento. Perciò dovrà offrire un sistema di API per fare effettuare le verifiche alle biblioteche localmente.

## Servizio di Tesseramento 

Il portale offre agli utenti vari servizi di tesseramento, alcuni a pagamento e altri gratuiti. Ogni tessera permette di accedere a dei servizi e dei vantaggi:

- Bibliopass
(tessera gratuita con possibilità di iscrizione/rinnovo on-line)

Richiedono, invece, il pagamento di una quota di adesione annuale:
	
 - Bibliocard
(10 euro l’anno)
	
- Youngcard
(5 euro l’anno - per utenti fino a 14 anni)
	
- Goldcard
(quota di sottoscrizione libera a partire da 20 euro l’anno)
La tessera d’iscrizione è personale e ha validità di un anno dall’ emissione.

Se si perde la tessera la si deve bloccare subito. In biblioteca verranno rilasciate nuove credenziali e verrà emessa una nuova tessera per avere nuovamente accesso a tutte le attività on-line. Il rilascio della tessera sostitutiva Bibliocard richiede il pagamento di un rimborso spese di 5 euro. In caso di furto la tessera sostitutiva è gratuita se viene presentata copia della denuncia.

##  Notizie

Il portale avrà anche una parte dedicata alle notizie. Questo avverrà sia in maniera aggregata e generale, nella sezione principale, sia in dettaglio e in riferimento alla singola biblioteca nella pagina dedicata ad essa. 

## Posizione 
Il portale dovrà segnalare le posizioni delle varie biblioteche, offrendo una chiara e semplice mappa delle posizioni. L'utente deve avere la possibilità di interagirci senza modificarla, possibilmente verificando quale sia la più vicina a lui in base al municipio di appartenenza. 

## Database Unificati
Il portale deve permettere di interrogare tutti i database delle varie biblioteche tramite un unico punto di accesso, questo per assicurare che ogni informazione sia condivisa e accessibile. 

## Integrare i servizi del Login di stato
Lo stato italiano ha da poco aggiunto vari servizi certificati, che permettono il login autorizzato del cittadino. Strumenti come lo SPID o la CIE, permettono un veloce e sicuro login da parte dell'utente che in applicazioni statali, come il portale descritto in questi file, sono indispensabili. 

## Gamification
Il portale dovrà aggiungere funzionalità di gamification. Gli utenti dovranno collaborare all'interno del portale per acquisire punti, questi potranno essere guadagnati tramite varie operazione tra cui: 
- Aggiunta di informazioni riguardanti i libri 
- Recensioni
- Prestiti
- Interazioni con la piattaforma

Ovviamente il sistema serve anche a punire comportamenti nocivi quali:
- Recensioni valutate negativamente dai librai
...

Alla conquista di una certa somma di punti l'utente potrà riscattare dei premi dalla seguente lista:
|Azione| Punteggio|
|---|---|
|Nuova/rinnovo BIBLIOPASS| 5.000|
|Nuova/rinnovo BIBLIOPASS online| 6.000|
|Nuova/rinnovo BIBLIOCARD| 10.000|
|Nuova/rinnovo BIBLIOCARD online| 11.000|
|Nuova/rinnovo YOUNGCARD| 10.000|
|Nuova/rinnovo YOUNGCARD online| 11.000|
|Nuova/rinnovo GOLDCARD| 15.000|
|Nuova/rinnovo GRATISCARD| 10.000|
|Nuova/rinnovo GRAYOUCARD| 10.000|
|Nuova/rinnovo SOCIALCARD| 10.000|
|Registrazione prestito Audiovisivo (DVD, CD, ... )| 100|
|Riconsegna prestito nei tempi previsti Audiovisivo| 100|
|Registrazione prestito tutti gli altri materiali (libro, e-book, ...)| 500|
|Riconsegna prestito nei tempi previsti tutti gli altri materiali| 700|
|Riconsegna prestito in ritardo| -1.000|
|Inserimento giudizio di gradimento sui titoli (stelle)| 50|
|Inserimento Commento| 1.000|
|Cancellazione commento| -1.000|
|Tuo commento ritenuto utile (Hai trovato utile questo commento?)| 300|
|Tuo commento ritenuto inopportuno dai bibliotecari| -1.000|
|Giudizio sui commenti di altri lettori (Hai trovato utile questo commento?)| 50|
|Condivisione Social (Facebook, Twitter)| 200|
|Utilizzo della nuova APP| 1.500|


## Revisioni
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|15/03/2025|Prima stesura del documento
<!---
Se le modifiche di Ganzio vanno bene per tutti, sistemare ed aggiungere questo commento
|1.1|19/03/2025|Modifiche generali: modificati requisiti (aggiunti nuovi requisiti, sistemati ed approfonditi quelli già presenti), aggiunto concetto di gamification.
--->