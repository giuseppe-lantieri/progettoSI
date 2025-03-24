# Biblioteche di Roma
# Gestione dei rischi

## Introduzione
Per la gestione dei rischi relativi al presente progetto si è scelto il modello **RMMM (Risk Mitigation, Monitoring and Management)**, che prevede l'identificazione dei principali rischi potenziali, la definizione di strategie preventive (mitigation), il monitoraggio periodico della situazione (monitoring), e la pianificazione delle azioni correttive in caso di problemi (management).

## Struttura delle tabelle
<!--- TODO completare paragrafo-->

## Elenco dei rischi
<!--- TODO completare paragrafo -->

#### Primo rischio
|||
|--|--|
|Campo|Contenuto|
|ID|R1
|Titolo|...
|Probabilità|...
|Effetti|...
|Descrizione|...
|Mitigation|...
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
|2.0|21/03/2025|Modifica stesura del documento iniziato da Giovanni