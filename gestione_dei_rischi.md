# Biblioteche di Roma
# Gestione dei Rischi

## Introduzione
Per gestire i rischi relativi al presente progetto si è scelto il modello **RMMM (Risk Mitigation, Monitoring and Management)**, il quale prevede:
- L’identificazione dei principali rischi potenziali;
- La definizione di strategie preventive (mitigation);
- Il monitoraggio periodico della situazione (monitoring);
- La pianificazione delle azioni correttive da intraprendere in caso di concretizzazione del rischio (management).

## Struttura delle Tabelle
Di seguito vengono illustrati i campi che compongono la tabella di gestione dei rischi:

- **ID:** Codice identificativo del rischio.
- **Titolo:** Breve descrizione del rischio.
- **Probabilità:** Indica la probabilità che il rischio si verifichi, definita secondo la seguente scala:
  - **Alta (70% - 100%):** Il rischio è altamente probabile e richiede un intervento tempestivo.
  - **Media (40% - 69%):** Il rischio potrebbe verificarsi occasionalmente; è consigliabile predisporre misure preventive.
  - **Bassa (10% - 39%):** Il rischio ha una probabilità ridotta di manifestarsi, ma va monitorato periodicamente.
  - **Molto Bassa (<10%):** Il rischio è estremamente improbabile e generalmente non richiede particolari attenzioni.
- **Effetti:** <!--- TODO: aggiungere scala di valori effetti --->
- **Descrizione:** Spiegazione dettagliata del rischio, con indicazioni sui contesti o le situazioni in cui potrebbe manifestarsi.
- **Mitigation:** Azioni preventive per ridurre la probabilità o l’impatto negativo del rischio.
- **Monitoring:** Modalità di monitoraggio periodico per verificare l’evoluzione del rischio, con indicazioni su quando e come effettuarne il controllo.
- **Management:** Attività e piani correttivi da attivare nel caso in cui il rischio si concretizzi.

## Elenco dei Rischi
#### Primo Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R1                                                                                          |
| **Titolo**      | Cambiamenti nei requisiti di progetto                                                       |
| **Probabilità** | Alta                                                                                        |
| **Effetti**     | Seri |
| **Descrizione** | Possibilità che i requisiti iniziali del progetto subiscano modifiche durante lo sviluppo, a causa di nuove richieste o di esigenze mutate degli stakeholder. |
| **Mitigation**  | Definizione precisa e documentata dei requisiti, adozione di metodologie agili e revisione periodica dei requisiti. |
| **Monitoring**  | Monitoraggio continuo delle richieste degli stakeholder, uso di strumenti di gestione dei requisiti, riunioni regolari con il cliente.                                                                                         |
| **Management**  | Adattamento del piano di progetto, assegnazione di buffer temporali per gestire modifiche, coinvolgimento tempestivo del team nella valutazione dei cambiamenti.                                                                                        |

#### Secondo Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R2                                                                                          |
| **Titolo**      | Incompatibilità con API o Database                                                          |
| **Probabilità** | Media                                                                                       |
| **Effetti**     | Seri             |
| **Descrizione** | Possibili difficoltà nell’integrazione del software con il database delle biblioteche o con API di terze parti. |
| **Mitigation**  | Esecuzione di test preliminari di compatibilità e sviluppo di soluzioni di fallback in caso di errore. |
| **Monitoring**  | Controllo periodico dei log di errore e monitoraggio delle prestazioni delle chiamate API.    |
| **Management**  | Predisposizione di un piano d'emergenza che preveda soluzioni temporanee o alternative.       |

#### Terzo Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R3                                                                                          |
| **Titolo**      | Scarsa accessibilità e usabilità                                                            |
| **Probabilità** | Media                                                                                       |
| **Effetti**     | Tollerabili |
| **Descrizione** | Il sito deve risultare accessibile anche a persone con disabilità visive o motorie, per garantire l'inclusività. |
| **Mitigation**  | Adozione delle linee guida WCAG per l’accessibilità e test con utenti reali.                  |
| **Monitoring**  | Verifica periodica del rispetto delle normative e analisi del feedback degli utenti.         |
| **Management**  | Rilascio di aggiornamenti mirati a migliorare l’accessibilità in caso di segnalazioni.         |

#### Quarto Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R4                                                                                          |
| **Titolo**      | Downtime temporaneo del sistema                                                           |
| **Probabilità** | Bassa                                                                                       |
| **Effetti**     | Seri                      |
| **Descrizione** | Il sistema potrebbe subire interruzioni temporanee a seguito di aggiornamenti, manutenzioni programmate o problemi momentanei del server. |
| **Mitigation**  | Implementazione di un'infrastruttura cloud scalabile, con server di backup e comunicazioni tempestive in caso di manutenzioni. |
| **Monitoring**  | Monitoraggio continuo dei server con sistemi automatici di alert (es. uptime robot, strumenti di monitoring cloud), log degli eventi di sistema, controlli giornalieri.                                                                                        |
| **Management**  | Attivazione rapida dei server di backup in caso di guasto, notifica immediata agli utenti, e pianificazione delle manutenzioni in orari di bassa attività.                                                                                   |

#### Quinto Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R5                                                                                          |
| **Titolo**      | Indisponibilità del personale                                                          		|
| **Probabilità** | Bassa                                                                                      |
| **Effetti**     | Tollerabili                          |
| **Descrizione** | Assenza temporanea o prolungata di membri chiave del team (per malattia, imprevisti o dimissioni) che potrebbero rallentare lo sviluppo e compromettere la continuità del progetto.
| **Mitigation**  | Pianificare in anticipo sostituzioni o turnazioni, garantire il cross-training e definire procedure per la gestione delle assenze. |
| **Monitoring**  | Monitoraggio continuo delle assenze tramite incontri periodici e report settimanali.|
| **Management**  | Ri-assegnare le attività ai membri disponibili o, se necessario, coinvolgere risorse esterne per minimizzare l’impatto.

### Sesto rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R6                                                                                          |
| **Titolo**      | Documentazione tecnica incompleta                                                        	|
| **Probabilità** | Media                                                                                       |
| **Effetti**     | Tollerabili/Seri                          |
| **Descrizione** | La documentazione, se non aggiornata o redatta in modo poco chiaro, può causare errori di implementazione e difficoltà di manutenzione, impattando negativamente il progetto.
| **Mitigation**  | 	Stabilire un processo di revisione periodica della documentazione, assegnando responsabilità chiare per la sua redazione e aggiornamento. |
| **Monitoring**  | Effettuare audit regolari del materiale documentale e raccogliere feedback dagli sviluppatori e dagli stakeholder.|
| **Management**  | Organizzare sessioni di aggiornamento e formazione, rivedendo tempestivamente la documentazione in base alle necessità emergenti.

### Settimo rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R7                                                                                          
| **Titolo**      | Violazioni della sicurezza dei dati                                                     		|
| **Probabilità** | Bassa/Media                                                                                |
| **Effetti**     | Seri/Catastrofici                       															|
| **Descrizione** | Possibile accesso non autorizzato o furto di dati sensibili degli utenti e della biblioteca, con conseguenze legali e reputazionali molto gravi.
| **Mitigation**  | Implementare robuste misure di sicurezza: crittografia, autenticazione a due fattori, controlli di accesso e aggiornamenti regolari del sistema.
| **Monitoring**  | Effettuare audit di sicurezza periodici, utilizzare strumenti di monitoraggio per rilevare anomalie e controllare costantemente i log di accesso.|
| **Management**  | Predisporre un piano d’intervento d’emergenza per isolare e risolvere il problema, comunicare tempestivamente agli stakeholder e pianificare azioni correttive.

## Revisioni

| Versione | Data       | Descrizione                        |
|----------|------------|------------------------------------|
| 1.0      | 20/03/2025 | Prima stesura del documento        |
| 1.1      | 21/03/2025 | Seconda stesura del documento      |
| 1.2      | 12/04/2025 | Terza stesura del documento        | 