# Biblioteche di Roma
# Gestione dei rischi

## Introduzione
Per la gestione dei rischi relativi al presente progetto si è scelto il modello **RMMM (Risk Mitigation, Monitoring and Management)**, che prevede l'identificazione dei principali rischi potenziali, la definizione di strategie preventive (mitigation), il monitoraggio periodico della situazione (monitoring), e la pianificazione delle azioni correttive in caso di problemi (management).

## Struttura delle tabelle
In questo paragrafo vengono spiegati tutti i punti presenti nella tabella dei rischi.

- **ID**: codice identificativo del rischio

- **Titolo**: breve nome che descrive il rischio

- **Probabilità**: indica quanto è possibile che il rischio si verifichi. E' definita attraverso la seguente scala:
	- **Alta (70% - 100%)**: il rischio ha un'alta probabilità di verificarsi ed è necessario intervenire tempestivamente
	- **Media (40% - 69%)**: il rischio potrebbe verificarsi occasionalmente ed è consigliabile predisporre misure preventive
	- **Bassa (10% - 39%)**: il rischio ha una scarsa probabilità di verificarsi, ma va monitorato periodicamente
	- **Molto Bassa (<10%)**: il rischio è estremamente improbabile e generalmente non richiede particolari attenzioni 

- **Effetti**: descrive le possibili conseguenze negative se il rischio dovesse concretizzarsi

- **Descrizione**: una spiegazione più dettagliata del rischio, con eventuali contesti o situazioni in cui potrebbe manifestarsi

- **Mitigation**: azioni preventive che possono essere intraprese per ridurre la probabilità o gli effetti negativi del rischio

- **Monitoring**: modalità di monitoraggio periodico per controllare se il rischio si sta manifestando, con indicazioni su quando e come controllarlo

- **Management**: attività da svolgere nel caso in cui il rischio si concretizzi. Include azioni correttive e piani per gestire efficacemente il problema una volta che si verifica

## Elenco dei rischi
<!--- TODO completare paragrafo -->

#### Primo rischio
|||
|--|--|
|Campo|Contenuto|
|ID|R1
|Titolo|Cambiamenti nei requisiti di progetto
|Probabilità|Alta
|Effetti|Ritardi nella consegna del prodotto finale, maggiori costi di sviluppo, necessità di rilavorare parti del software già implementate.
|Descrizione|Possibilità che i requisiti iniziali del progetto cambino durante lo sviluppo a causa di nuove richieste, esigenze mutate degli stakeholder o requisiti non definiti chiaramente nella fase iniziale.
|Mitigation|Definizione precisa e documentata dei requisiti iniziali, adozione di metodologie agili, revisione periodica dei requisiti
|Monitoring|...
|Management|...

#### Secondo rischio
|||
|--|--|
|Campo|Contenuto|
|ID|R2
|Titolo|Incompatibilità con API o Database
|Probabilità|Media
|Effetti|Errori di sincronizzazione, mancata comunicazione tra sistemi, dati incoerenti
|Descrizione|Il software potrebbe avere problemi a interfacciarsi con il database delle biblioteche o con API di terze parti
|Mitigation|Test preliminari di compatibilità, sviluppo di fallback in caso di errore
|Monitoring|Controllo periodico dei log di errore e delle prestazioni delle chiamate API
|Management|Creazione di un piano di emergenza che preveda workaround temporanei o soluzioni alternative

#### Terzo rischio
|||
|--|--|
|Campo|Contenuto|
|ID|R3
|Titolo|Scarsa Accessibilità e Usabilità
|Probabilità|Media
|Effetti|Difficoltà per gli utenti a navigare nel sito, lamentele, ridotto utilizzo del software
|Descrizione|Il sito deve essere fruibile anche da persone con disabilità visive o motorie, altrimenti potrebbero esserci problemi di inclusività
|Mitigation|Applicazione delle linee guida WCAG per l’accessibilità, test con utenti reali
|Monitoring|Verifica periodica del rispetto delle normative e analisi del feedback degli utenti
|Management|Rilascio di aggiornamenti per migliorare l’accessibilità in caso di segnalazioni

#### Quarto rischio
|||
|--|--|
|Campo|Contenuto|
|ID|R4
|Titolo|Downtime Temporaneo del Sistema
|Probabilità|Bassa
|Effetti|Breve indisponibilità del software, possibili disagi per gli utenti
|Descrizione|Il sistema potrebbe subire brevi interruzioni a causa di aggiornamenti, manutenzioni programmate o problemi momentanei del server
|Mitigation|Implementazione di un'infrastruttura cloud scalabile con server di backup e notifiche agli utenti in caso di manutenzione programmata
|Monitoring|...
|Management|...

## Revisioni
||||
|--|--|--|
|Versione|Data|Descrizione|
|1.0|20/03/2025|Prima stesura del documento
|1.1|21/03/2025|Seconda stesura del documento
