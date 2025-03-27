# Biblioteche di Roma
### Studio di fattibilità
## Scopo del documento
Questo documento ha lo scopo di analizzare il background e i problemi dell'ambiente in cui si inserisce il software, i vantaggi e svantaggi, un'analisi di mercato, i costi e le tecnologie utilizzate per l'implementazione.

## Formulazione del problema
L'ambiente in cui si inserisce il software per la gestione delle biblioteche di Roma è caratterizzato da una forte rigidità, meccanicità e soprattutto da una frammentazione delle informazioni. Infatti ogni biblioteca gestisce autonomamente cataloghi e archivi locali, generando duplicazioni, errori di catalogazione e inconsistenza dei dati. L'assenza di un catalogo centralizzato rende complicato per gli utenti individuare rapidamente la disponibilità e la collocazione delle opere, costringendoli spesso a rivolgersi fisicamente a più strutture per reperire informazioni precise. Questo sistema frammentato comporta inoltre procedure manuali lente e inefficienti per prestiti, rinnovi e iscrizioni, soggette a frequenti errori umani. Di conseguenza, le risorse bibliografiche risultano poco accessibili e scarsamente valorizzate, con un patrimonio culturale difficilmente fruibile dall’utenza e scarsamente promosso.

## Soluzione
La soluzione proposta per risolvere questi problemi consiste nella realizzazione di una piattaforma digitale centralizzata, accessibile tramite web, che unifica in un unico ambiente informatico le informazioni e i servizi di tutte le biblioteche del sistema romano. Questa soluzione prevede un catalogo online integrato (OPAC), permettendo agli utente di cercare facilmente le risorse bibliografiche disponibili, verificarne la collocazione, lo stato del prestito, e gestire autonomamente prenotazioni e rinnovi direttamente online.

## Vantaggi
La centralizzazione delle informazioni riduce drasticamente duplicazione ed errori. Gli utenti possono consultare in maniere semplice ed immediata il catalogo online, evitando spostamenti inutili e migliorando l'esperienza utente. Inoltre, automatizzando le procedure gestionali e il prestito interbibliotecario, il sito semplifica e velocizza il lavoro del personale, riducendo al minimo gli errori manuali. Infine, la piattaforma consente una maggiore valorizzazione e visibilità del patrimonio bibliografico e culturale, promuovendo servizi, eventi e iniziative delle biblioteche verso un pubblico più ampio e diversificato.

## Svantaggi
Tra gli svantaggi della soluzione proposta da "Biblioteche di Roma" vi è il costo iniziale elevato, dovuto agli investimenti necessari per lo sviluppo della piattaforma digitale, la migrazione dei dati, l’acquisto delle infrastrutture tecnologiche e la formazione del personale. A questo si aggiunge la necessità di prevedere un piano continuo di manutenzione e aggiornamento, con costi periodici associati e la disponibilità di personale tecnico qualificato che garantisca nel tempo l'efficienza e il corretto funzionamento del sistema.

## Analisi di mercato
Nel contesto della capitale Italiana il panorama risulta frammentato, con software non uniformi e spesso non integrati tra loro. Perciò la richiesta di una soluzione unificata è fortemente sentita sia dalle istituzioni che dagli utenti. La piattaforma proposta risponde dunque alla crescente domanda di sistemi centralizzati, più efficienti e user-friendly.

## Tecnologie
Per la realizzazione del sistema si prevede l'utilizzo delle seguenti componenti tecnologiche:
	- Un'interfaccia web, che consenta agli utenti di accedere ai servizi offerti; 
	- Un web server, incaricato di gestire le richieste provenienti dal client e coordinare la comunicazione con la base dati;
	- Un database relazionale, necessario per conservare in modo strutturato le informazioni relative a utenti, libri, disponibilità e prestiti.

Trattandosi di un sistema basato su tecnologie ampiamente diffuse e consolidate, non si rende necessario introdurre strumenti innovativi o sperimentali. 
Il linguaggio principale adottato sarà Java 8, la gestione dei dati avverrà tramite comandi SQL, mentre la realizzazione dell'interfaccia utente sarà affidata a HTML5, con il possibile supporto di CSS3 e JavScript per una maggiore dinamicità e responsività dell'esperienza utente.

## Revisioni
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|19/03/2025|Prima stesura del documento