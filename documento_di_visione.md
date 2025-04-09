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

Il portale offrirà una sezione accessibile solo al personale autorizzato, in cui sarà possibile effettuare operazioni di carattere amministrativo tra cui:
- Operare sui libri presenti
- Segnalare problemi negli spazi condivisi
- Operare sull'interfaccia del profilo biblioteca
<br/>

Oltre a ciò il portale deve essere in grado di:
- Permettere i login tramite i servizi di stato
- Aggregare i database
- Gamification 

## ***PRENOTAZIONE LIBRI*** 
Il portale deve permettere ai vari utenti (che abbiano effettuato o meno l'accesso) di verificare la presenza dei libri, indicando se sono fisici o ebook. 
Nel caso di libri fisici dovrà aggiungere le informazioni riguardanti la libreria che lo possiede, la posizione e indicare la prima disponibilità.
Nel caso il libro risultasse già preso, l'utente potrà aumentare i giorni del prestito a meno di una prenotazione effettuata alla prima disponibilità.

## ***PRESTITO LIBRI***
Il prestito libri differisce in base al formato del libro:
- Fisico: 
	
	Il libro fisico non potrà per ovvie ragione essere preso direttamente online, il portale per permettere il servizio a seguito di una prenotazione, dovrà:
	
	1) Segnalare la prima indisponibilità del libro per 14 giorni 
	2) Creare una ricevuta da inviare all'utente da utilizzare alla consegna
	3) Permettere al bibliotecario di convalidare l'autenticità della ricevuta
	4) Impedire agli altri utenti di prenotare a loro volta il libro prima della scadenza della prenotazione
	5) Permettere all'utente che ha effettuato la prenotazione di allungare il prestito in assenza di altre prenotazioni

- Ebook: 
	Il libro digitale avrà differenti termini di prestito in base alla licenza e i termini di utilizzo che la biblioteca ha stabilito con il produttore. In caso di prenotazione il portale avrà differenti comportamenti in base alla licenza.
	Qui illustriamo due comportamenti, ma in seguito potrebbero esserne presenti di più:
	
	1) Licenza di libera distribuzione e fruizione: l'ebook verrà consegnato all'utente in una copia firmata e senza il permesso di ridistribuzione
	2) Licenza di sola lettura: l'ebook sarà visionabile in una sezione del profilo dell'utente per la durata di 14 giorni in solo lettura, si utilizzeranno le tecnologie migliori per evitare comportamenti che violino i requisiti. 

## ***PRENOTAZIONE POSTO***

Alcune biblioteche offrono tavoli e sale, adibite al co-working e allo studio. 
Il portale dovrà:
1) Segnalare se la biblioteca scelta ha un posto disponibile
2) Gestire la prenotazione anche in caso di concorrenza
3) Permettere la verifica di quest'ultima da parte di un bibliotecario
4) Segnalare al bibliotecario la fine di una prenotazione in modo che esso possa controllare
5) Permettere all'utente di estendere la propria prenotazione

## ***SERVIZIO DI TESSERAMENTO*** 

Il portale offre agli utenti vari servizi di tesseramento, alcuni a pagamento e altri gratuiti.
La tessera d’iscrizione è personale e ha una validità fissa. 

I bibliotecari possono creare tessere per i nuovi utenti, proporre la creazione di una nuova tipologia di tessera e chiedere l'annullamento di una tessera di un utente.

##  ***NOTIZIE***

Il portale ha una sezione dedicata alle notizie. Questo avviene sia in maniera aggregata e generale, nella sezione principale, sia in dettaglio e in riferimento alla singola biblioteca nella pagina dedicata ad essa. 

## ***POSIZIONE*** 
Il portale deve offrire una chiara e semplice mappa delle biblioteche, indicando per ognuna posizione e indicazioni. L'utente deve avere la possibilità di interagire con essa senza modificarla, identificando la più vicina a lui in base al municipio di appartenenza. 

## ***DATABASE UNIFICATI***
Il portale deve permettere di interrogare tutti i database delle varie biblioteche tramite un unico punto di accesso, per assicurare che ogni informazione sia condivisa e accessibile. 

Per permettere ciò i database già esistenti verranno incorporati nel database che verrà generato per l'applicazione. 

Inoltre sarà assicurata una migliore gestione dei dati. Verranno adottate le soluzioni più moderne, assicurando backup frequenti e politiche di distribuzione, adottando anche le regole descritte nel progetto OPEN DATA. 

## ***INTEGRARE I SERVIZI DEL LOGIN DI STATO***
Lo stato italiano dispone di vari servizi certificati, che permettono il login autorizzato del cittadino. Strumenti come lo SPID o la CIE, permettono un veloce e sicuro login da parte dell'utente che in applicazioni statali, come il portale descritto in questi file, sono indispensabili. 

## ***GAMIFICATION***
Il portale dovrà aggiungere funzionalità di gamification. Gli utenti dovranno collaborare all'interno del portale in apposite sezioni per acquisire punti tramite varie operazione tra cui: 
- Aggiunta di informazioni riguardanti i libri
- Recensioni
- Prestiti
- Interazioni con la piattaforma

Il sistema serve anche a punire comportamenti nocivi quali:
- Recensioni valutate negativamente dai librai
- Smarrimento di un libro
- Ritardo nella riconsegna di un libro
- Riconsegna di un libro con segni di usura

Al raggiungimento di una certa somma di punti l'utente potrà riscattare dei premi, segue un esempio:  

|Azione| Punteggio|
|---|---|
|Tuo commento ritenuto utile | 300|
|Tuo commento ritenuto inopportuno dai bibliotecari| -1.000|

Il sistema sarà progettato per portare maggiore interazione dell'utente con la piattaforma e valorizzare le biblioteche per le nuove generazioni. 

Per assicurare ciò le nuove sezioni del portale dedicate alla gamification saranno ottimizzate per la visione mobile. 

## ***REVISIONI***
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|15/03/2025|Prima stesura del documento|
|1.1|19/03/2025|Seconda stesura del documento|
|1.2|25/03/2025|Terza stesura del documento|
|1.3|09/04/2025|Quarta stesura del documento|