# BIBLIOTECHE DI ROMA
### STUDIO DI FATTIBILITÀ

## SCOPO DEL DOCUMENTO
Il presente documento ha l’obiettivo di analizzare il contesto e le problematiche relative all’ambiente in cui verrà implementato il software per la gestione delle biblioteche di Roma. In particolare, vengono esaminati il background operativo, i vantaggi e gli svantaggi del sistema attuale, l’analisi di mercato, i costi stimati e le tecnologie impiegate per l’implementazione.

## FORMULAZIONE DEL PROBLEMA
L’ambiente in cui sarà inserito il software per la gestione delle biblioteche di Roma presenta diverse criticità, quali:
- **Rigidità e meccanicità:** Ogni biblioteca gestisce autonomamente i propri cataloghi e archivi, con conseguenti duplicazioni, errori di catalogazione e incoerenze tra i dati.
- **Fragmentazione delle informazioni:** L’assenza di un catalogo centralizzato complica il reperimento rapido della disponibilità e della collocazione delle risorse, costringendo gli utenti a rivolgersi fisicamente a più strutture.
- **Procedure manuali:** I processi di prestito, rinnovo e iscrizione sono gestiti manualmente, rendendo il sistema soggetto a errori umani e rallentamenti.

Queste problematiche limitano l’accessibilità delle risorse bibliografiche e la valorizzazione del patrimonio culturale, compromettendo l’efficacia dei servizi offerti.

## SOLUZIONE
La soluzione proposta consiste nella realizzazione di una piattaforma digitale centralizzata, accessibile via web, che integri in un unico ambiente informativo tutti i servizi e le informazioni delle biblioteche del sistema romano. Nello specifico, la piattaforma prevede:
- Un catalogo online integrato (OPAC) per facilitare la ricerca e la consultazione delle risorse bibliografiche.
- La possibilità per gli utenti di gestire autonomamente prenotazioni, prestiti e rinnovi tramite interfacce intuitive.
- L’automatizzazione delle procedure gestionali, al fine di ridurre errori e velocizzare le operazioni quotidiane.

## VANTAGGI
L’adozione della piattaforma digitale comporta numerosi benefici:
- **Centralizzazione delle informazioni:** Eliminazione delle duplicazioni e delle incoerenze, con una gestione dati più efficiente.
- **Esperienza utente migliorata:** Gli utenti potranno consultare il catalogo online in modo semplice e immediato, riducendo spostamenti e tempi di attesa.
- **Ottimizzazione dei processi:** L’automazione delle attività di prestito e rinnovo ridurrà gli errori manuali, alleggerendo il carico di lavoro del personale.
- **Valorizzazione del patrimonio culturale:** Maggiore visibilità e accessibilità per le risorse bibliografiche, contribuendo alla promozione di eventi e iniziative culturali.

## SVANTAGGI
Tra le criticità della soluzione proposta si evidenziano:
- **Elevato investimento iniziale:** I costi per lo sviluppo della piattaforma, la migrazione dei dati, l’acquisto delle infrastrutture tecnologiche e la formazione del personale risultano significativi.
- **Costi di manutenzione:** È necessario predisporre un piano di aggiornamento e manutenzione continuo, con costi periodici e la necessità di personale tecnico qualificato per garantire il corretto funzionamento del sistema.

## ANALISI DI MERCATO
Nel contesto della Capitale Italiana il panorama risulta estremamente frammentato, con soluzioni software non uniformi e non integrate tra loro. La crescente domanda di sistemi centralizzati, efficienti e user-friendly, è evidente sia tra le istituzioni sia tra gli utenti, rendendo la proposta particolarmente attuale e necessaria.

## TECNOLOGIE
Per la realizzazione del sistema si prevede l’utilizzo delle seguenti componenti tecnologiche:
- **Interfaccia Web:** Permetterà agli utenti l’accesso ai servizi offerti; la sezione amministrativa sarà protetta da certificati, garantendo l’accesso esclusivo ai dispositivi autorizzati.
- **Web Server:** Gestirà le richieste provenienti dai client e coordinerà la comunicazione con il database.
- **Base Dati:** Un database relazionale strutturato per conservare in modo sicuro e organizzato informazioni relative a utenti, libri, disponibilità e prestiti.

La piattaforma si baserà su tecnologie consolidate: il linguaggio principale sarà Go, la gestione dei dati avverrà tramite comandi SQL e l’interfaccia utente sarà sviluppata con Vue.

### RAGIONI PER LA SCelta
- **Interfaccia Web:** L’utilizzo di Vue.js per lo sviluppo dell’interfaccia web è motivato dalla sua popolarità, flessibilità e potenza di reazione. La libreria permette la creazione di componenti riutilizzabili e una gestione efficiente dello stato, garantendo un’esperienza utente fluida.
- **Web Server:** Il linguaggio Go (Golang) è stato scelto per il suo elevato livello di performance e flessibilità. La sua sintassi elegante e la capacità di gestire operazioni concorrenti in modo efficiente lo rendono ideale per un sistema che deve gestire molte richieste simultanee.
- **Base Dati:** L’utilizzo di un database relazionale (PostgreSQL) è motivato dalla necessità di gestire strutture dati complesse e interrelate. La sua capacità di supportare transazioni atomiche e di garantire integrità referenziale fa sì che i dati siano conservati in modo sicuro e coerente.

Questo stack tecnologico permette di sviluppare un sistema robusto, scalabile e facile da mantenere, adatto a gestire le esigenze di un ampio range di utenti.

## COSTI
La realizzazione della piattaforma comporta costi significativi che includono:
- Sviluppo del software e migrazione dei dati.
- Acquisto, configurazione e manutenzione dell’hardware necessario.
- Formazione del personale e supporto tecnico.
- Spese ricorrenti per l’aggiornamento e la manutenzione del sistema.

## CALCOLO DEI SERVER FISICI
Per garantire un servizio stabile e affidabile, è essenziale dimensionare correttamente l’infrastruttura hardware. Il calcolo dei server fisici si basa sui seguenti parametri:

- **Numero di utenti contemporanei:** Una stima del carico massimo previsto, che determina il volume di richieste da elaborare.
- **Volume dei dati:** La quantità di informazioni da gestire incide sulle esigenze di capacità di storage ed elaborazione.
- **Ridondanza e scalabilità:** È necessaria una configurazione che preveda backup e sistemi di load balancing per garantire la continuità del servizio in caso di guasti.

Una metodologia per il dimensionamento è la seguente:
1. **Analisi del traffico:** Determinare il numero medio e di picco degli utenti attivi e il volume delle richieste.
2. **Definizione delle risorse per server:** Utilizzare benchmark e test preliminari per stabilire le capacità (CPU, memoria, storage) richieste per ogni server.
3. **Formula di dimensionamento:**  
   \[
   N = \lceil \frac{U_{max}}{C} \rceil
   \]
   dove \( N \) rappresenta il numero di server fisici necessari, \( U_{max} \) il massimo numero di utenti simultanei, e \( C \) la capacità operativa di ogni server.
4. **Implementazione della ridondanza:** Prevedere almeno un server in più per garantire il failover e la continuità del servizio in caso di malfunzionamenti.

Questa analisi, integrata da test di carico e monitoraggio continuo, permetterà di ottimizzare il dimensionamento dell’infrastruttura in base alle reali esigenze operative.

## REVISIONI
| Versione | Data       | Descrizione                       |
|----------|------------|-----------------------------------|
| 1.0      | 19/03/2025 | Prima stesura del documento       |
| 1.1      | 25/03/2025 | Seconda stesura del documento     |
| 1.2      | 09/04/2025 | Terza stesura del documento       |
