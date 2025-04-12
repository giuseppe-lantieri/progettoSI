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
- **Effetti:** Descrive le possibili conseguenze negative in caso di concretizzazione del rischio.
- **Descrizione:** Spiegazione dettagliata del rischio, con indicazioni sui contesti o le situazioni in cui potrebbe manifestarsi.
- **Mitigation:** Azioni preventive per ridurre la probabilità o l’impatto negativo del rischio.
- **Monitoring:** Modalità di monitoraggio periodico per verificare l’evoluzione del rischio, con indicazioni su quando e come effettuarne il controllo.
- **Management:** Attività e piani correttivi da attivare nel caso in cui il rischio si concretizzi.

## Elenco dei Rischi

<!--- TODO: completare eventuali ulteriori osservazioni se necessario --->

#### Primo Rischio
|||
|-----------------|---------------------------------------------------------------------------------------------|
| **Campo**       | **Contenuto**                                                                               |
| **ID**          | R1                                                                                          |
| **Titolo**      | Cambiamenti nei requisiti di progetto                                                       |
| **Probabilità** | Alta                                                                                        |
| **Effetti**     | Ritardi nella consegna del prodotto finale, maggiori costi di sviluppo, rilavorazione di parti già implementate. |
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
| **Effetti**     | Errori di sincronizzazione, mancata comunicazione tra sistemi, dati incoerenti.             |
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
| **Effetti**     | Difficoltà di navigazione per gli utenti, possibili lamentele e ridotto utilizzo del software. |
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
| **Effetti**     | Breve interruzione del servizio e possibili disagi per gli utenti.                           |
| **Descrizione** | Il sistema potrebbe subire interruzioni temporanee a seguito di aggiornamenti, manutenzioni programmate o problemi momentanei del server. |
| **Mitigation**  | Implementazione di un'infrastruttura cloud scalabile, con server di backup e comunicazioni tempestive in caso di manutenzioni. |
| **Monitoring**  | Monitoraggio continuo dei server con sistemi automatici di alert (es. uptime robot, strumenti di monitoring cloud), log degli eventi di sistema, controlli giornalieri.                                                                                        |
| **Management**  | Attivazione rapida dei server di backup in caso di guasto, notifica immediata agli utenti, e pianificazione delle manutenzioni in orari di bassa attività.                                                                                   |

## Revisioni

| Versione | Data       | Descrizione                        |
|----------|------------|------------------------------------|
| 1.0      | 20/03/2025 | Prima stesura del documento        |
| 1.1      | 21/03/2025 | Seconda stesura del documento      |
