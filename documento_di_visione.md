# **BIBLIOTECHE DI ROMA**
### **DOCUMENTO DI VISIONE**
## ***INTRODUZIONE***
Il comune di Roma vuole creare un nuovo portale online per il proprio sistema bibliotecario. 
Il portale deve dare la possibilità di accedere ai servizi offerti dalle biblioteche in maniera semplice e digitale. 
L'obiettivo, perciò è riuscire a creare un semplice metodo per gli utenti di usufruire dei seguenti servizi:
- Prenotazione Libri
- Prestito Libri (fisico e ebook)
- Prenotazione Posto (ove possibile)
- Servizio Wi-Fi
- Servizio Tesseramento


Oltre a ciò il portale deve essere in grado di:
- Segnalare notizie riguardanti le singole biblioteche
- Offrire indicazioni chiare e veloci sulla posizione
- Aggregare i database
- Permettere i login tramite i servizi di stato
<!-- TODO Non ho idea se lasciarlo
- Aderire al servizio Open Data 
-->
- Gamification 

## ***PRENOTAZIONE LIBRI*** 
Il portale deve permettere ai vari utenti (che abbiano effettuato o meno l'accesso) di verificare la presenza dei libri, indicando se sono fisici o ebook, nel caso dovrà aggiungere le informazioni riguardanti la libreria che lo possiede e la posizione.
Nel caso il libro risultasse già preso, andrà specificato il numero di giorni mancanti alla fine del prestito.

## ***PRESTITO LIBRI***
Il prestito libri differisce in base al formato del libro:
- Fisico: 
	
	Il libro fisico non potrà per ovvie ragione essere preso direttamente online, il portale per permettere il servizio dovrà:
	
	1) Segnalare la presa in carico al database
	2) Creare una ricevuta apposita da consegnare all'utente
	3) Permettere al bibliotecario di convalidare l'autenticità della ricevuta
	4) Impedire agli altri utenti di prenotare a loro volta il libro

- Ebook: 
	Il libro digitale dovrà essere gestito interamente dal portale, per assicurare che i termini e le licenze dell'ebook non vengano violati deve limitare le interazione dell'utente con esso, ma permetterne comunque una lettura agevole e senza intralci.

## ***PRENOTAZIONE POSTO***

Alcune biblioteche offrono tavoli e sale, adibite al co-working e allo studio. 
Il portale dovrà:
1) Segnalare se la biblioteca scelta ha un posto disponibile
2) Gestire la prenotazione anche in caso di concorrenza
3) Permettere la verifica di quest'ultima da parte di un bibliotecario
4) Segnalare al bibliotecario la fine di una prenotazione in modo che esso possa controllare
5) Permettere all'utente di estendere la propria prenotazione

## ***SERVIZIO WI-FI*** 

Il portale deve offrire la possibilità di entrare all'interno della connessione protetta offerta dal comune di Roma. Il servizio è accessibile solo alle persone che hanno aderito a un certo livello di tesseramento, perciò dovrà offrire un sistema di API per fare effettuare le verifiche alle biblioteche localmente.

## ***SERVIZIO DI TESSERAMENTO*** 

Il portale offre agli utenti vari servizi di tesseramento, alcuni a pagamento e altri gratuiti. Ogni tessera permette di accedere a dati servizi e vantaggi:

- Bibliopass
(tessera gratuita con possibilità di iscrizione/rinnovo on-line)

Richiedono, invece, il pagamento di una quota di adesione annuale:
	
- Bibliocard
	
- Youngcard
	
- Goldcard
La tessera d’iscrizione è personale e ha validità di un anno dall’ emissione.

Se si perde la tessera la si deve bloccare subito. In biblioteca verranno rilasciate nuove credenziali e verrà emessa una nuova tessera per avere nuovamente accesso a tutte le attività on-line. Il rilascio della tessera sostitutiva Bibliocard richiede il pagamento di un rimborso spese di 5 euro. In caso di furto la tessera sostitutiva è gratuita se viene presentata copia della denuncia.

##  ***NOTIZIE***

Il portale ha una sezione dedicata alle notizie. Questo avviene sia in maniera aggregata e generale, nella sezione principale, sia in dettaglio e in riferimento alla singola biblioteca nella pagina dedicata ad essa. 

## ***POSIZIONE*** 
Il portale deve offrire una chiara e semplice mappa delle biblioteche, indicando per ognuna posizione e indicazioni. L'utente deve avere la possibilità di interagire con essa senza modificarla, identificando la più vicina a lui in base al municipio di appartenenza. 

## ***DATABASE UNIFICATI***
Il portale deve permettere di interrogare tutti i database delle varie biblioteche tramite un unico punto di accesso, per assicurare che ogni informazione sia condivisa e accessibile. 

## ***INTEGRARE I SERVIZI DEL LOGIN DI STATO***
Lo stato italiano ha da poco aggiunto vari servizi certificati, che permettono il login autorizzato del cittadino. Strumenti come lo SPID o la CIE, permettono un veloce e sicuro login da parte dell'utente che in applicazioni statali, come il portale descritto in questi file, sono indispensabili. 

## ***GAMIFICATION***
Il portale dovrà aggiungere funzionalità di gamification. Gli utenti dovranno collaborare all'interno del portale per acquisire punti tramite varie operazione tra cui: 
- Aggiunta di informazioni riguardanti i libri 
- Recensioni
- Prestiti
- Interazioni con la piattaforma

Il sistema serve anche a punire comportamenti nocivi quali:
- Recensioni valutate negativamente dai librai
- Smarrimento di un libro
- Ritardo nella riconsegna di un libro
- Riconsegna di un libro con segni di usura

Alla conquista di una certa somma di punti l'utente potrà riscattare dei premi dalla seguente lista:  
n.b.: il sistema di punteggio è indicativo
|Azione| Punteggio|
|---|---|
|Sottoscrizione/rinnovo BIBLIOPASS| 5.000|
|Tuo commento ritenuto utile (Hai trovato utile questo commento?)| 300|
|Tuo commento ritenuto inopportuno dai bibliotecari| -1.000|


## ***REVISIONI***
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|15/03/2025|Prima stesura del documento
|1.1|19/03/2025|Seconda stesura del documento
|1.2|25/03/2025|Terza stesura del documento
