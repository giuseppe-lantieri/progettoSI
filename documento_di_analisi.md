# Documento di Analisi – Gestione Biblioteche Romane

## 1. Introduzione
In questo documento viene descritta l’analisi del sistema per la gestione delle biblioteche romane. Il testo si articola in diverse sezioni:  
- Una descrizione preliminare del sistema;  
- L’analisi dei casi d’uso e la definizione del glossario;  
- L’estrazione delle classi di analisi tramite le schede CRC;  
- La rappresentazione delle relazioni mediante diagrammi EBC;  
- Infine, i diagrammi di sequenza.

## 2. Visione di Sistema
Il portale si configura come un sistema centralizzato, in grado di garantire la comunicazione tra diversi attori:

- **UtenteGuest** e **Utente**: Utenti finali che interagiscono con il sistema per cercare libri, effettuare prestiti, prenotare spazi e partecipare alle attività di gamification.  
- **Bibliotecario**: Operatore dotato di privilegi amministrativi, responsabile della gestione del catalogo, del monitoraggio dei prestiti e della pubblicazione di notizie.  
- **Servizio Esterno**: Sistema di integrazione con servizi di autenticazione esterni (ad es. CIE, SPID) che agevola l’accesso al portale.

La piattaforma garantisce una gestione centralizzata e sicura delle operazioni; per una corretta realizzazione, si procederà con l’analisi dei nomi e dei verbi e con la creazione delle schede CRC.

## 3. Attori e Casi d’Uso

### 3.1 Attori
Gli attori identificati sono desumibili in dettaglio dal documento dei modelli di caso d’uso.

### 3.2 Casi d’Uso
I casi d’uso sono descritti in maniera approfondita nel documento dei modelli di caso d’uso; in questa sezione si riportano solo gli identificativi (ID).

## 4. Analisi Nomi-Verbi
L’approccio “nomi-verbi” prevede di identificare le entità principali (sostantivi) e le azioni (verbi) che il sistema deve supportare. Di seguito sono elencate alcune delle principali entità e operazioni, estratte dall’analisi dei casi d’uso.

### 4.1 Entità (Nomi)
- **Utente**: astrazione che rappresenta l’Utente autenticato.
- **Bibliotecario**: utente con privilegi amministrativi.
- **Libro**: oggetto ricercabile, in prestito o disponibile per il prestito.
- **Prestito**: operazione relativa al prestito fisico o digitale dei libri (o ebook).
- **Tessera**: strumento che consente l’accesso a privilegi particolari.
- **Prenotazione**: richiesta di prenotazione per uno spazio comune.
- **Commento/Recensione**: feedback lasciato dagli utenti all’interno della sezione di gamification.
- **Biblioteca**: rappresentazione dell’istituzione, per la pubblicazione di notizie e la gestione degli spazi.

### 4.2 Azioni (Verbi)
Le principali operazioni individuate sono:
- **Autenticare**: gestire l’accesso al sistema (AU_1, AU_2).
- **Registrare**: inserimento di nuovi utenti (AU_4).
- **Modificare**: aggiornare password (AU_3) o profili (G_2).
- **Effettuare Logout**: terminare una sessione (AU_5).
- **Richiedere Tessera**: gestire le operazioni di tesseramento (T_1, T_2, T_3, T_4, T_5).
- **Partecipare**: iscriversi al sistema di gamification (G_1).
- **Commentare/Recensire**: inserire feedback sui libri (G_3).
- **Segnalare**: gestire problematiche (G_4, PS_3).
- **Riscattare**: riscattare punti (G_5).
- **Ricercare**: cercare libri e richiedere il prestito (PL_1).
- **Restituire**: restituire i libri (PL_2).
- **Richiedere Allungamento**: estendere il periodo di prestito (PL_3).
- **Richiedere e-book**: ottenere prestito digitale (PL_4).
- **Prenotare/Cancellare Prenotazione**: gestire le prenotazioni degli spazi (PS_1, PS_2).
- **Caricare**: inserire nuovi libri nel sistema (SA_1).
- **Segnalare Prestito e Notizie**: aggiornare lo stato del sistema (SA_2, SA_3).
- **Gestire**: personalizzare la pagina della biblioteca (SA_4).

## 5. Diagrammi di Attività
![AU_1](./img/diagrammi_di_attivita/AU_1.jpg)
![AU_2](./img/diagrammi_di_attivita/AU_2.jpg)
![AU_3](./img/diagrammi_di_attivita/AU_3.jpg)
![AU_4](./img/diagrammi_di_attivita/AU_4.jpg)
![AU_5](./img/diagrammi_di_attivita/AU_5.jpg)
![T_1](./img/diagrammi_di_attivita/T_1.jpg)
![T_2](./img/diagrammi_di_attivita/T_2.jpg)
![T_3](./img/diagrammi_di_attivita/T_3.jpg)
![T_4](./img/diagrammi_di_attivita/T_4.jpg)
![T_5](./img/diagrammi_di_attivita/T_5.jpg)
![G_1](./img/diagrammi_di_attivita/G_1.jpg)
![G_2](./img/diagrammi_di_attivita/G_2.jpg)
![G_3](./img/diagrammi_di_attivita/G_3.jpg)
![G_4](./img/diagrammi_di_attivita/G_4.jpg)
![G_5](./img/diagrammi_di_attivita/G_5.jpg)
![PL_1](./img/diagrammi_di_attivita/PL_1.jpg)
![PL_2](./img/diagrammi_di_attivita/PL_2.jpg)
![PL_3](./img/diagrammi_di_attivita/PL_3.jpg)
![PL_4](./img/diagrammi_di_attivita/PL_4.jpg)
![PS_1](./img/diagrammi_di_attivita/PS_1.jpg)
![PS_2](./img/diagrammi_di_attivita/PS_2.jpg)
![PS_3](./img/diagrammi_di_attivita/PS_3.jpg)
![SA_1](./img/diagrammi_di_attivita/SA_1.jpg)
![SA_2](./img/diagrammi_di_attivita/SA_2.jpg)
![SA_3](./img/diagrammi_di_attivita/SA_3.jpg)
![SA_4](./img/diagrammi_di_attivita/SA_4.jpg)

## 6. Diagrammi di Classe
![diagrammi_di_classe.jpg](./img/diagrammi_di_classe.jpg)

## 7. Diagrammi di Package
![diagrammi_di_classe.jpg](./img/diagrammi_package.jpg)

## 8. Schede CRC
![diagrammi_di_classe.jpg](./img/crc/CAmministrativo.jpg)
![diagrammi_di_classe.jpg](./img/crc/CEbook.jpg)
![diagrammi_di_classe.jpg](./img/crc/CGamification.jpg)
![diagrammi_di_classe.jpg](./img/crc/CPagineSito.jpg)
![diagrammi_di_classe.jpg](./img/crc/CPrenotazione.jpg)
![diagrammi_di_classe.jpg](./img/crc/CPrestiti.jpg)
![diagrammi_di_classe.jpg](./img/crc/CRicerche.jpg)
![diagrammi_di_classe.jpg](./img/crc/CServiziEsterni.jpg)
![diagrammi_di_classe.jpg](./img/crc/CTesseramento.jpg)
![diagrammi_di_classe.jpg](./img/crc/CUtenza.jpg)
![diagrammi_di_classe.jpg](./img/crc/EBiblioteca.jpg)
![diagrammi_di_classe.jpg](./img/crc/EBibliotecario.jpg)
![diagrammi_di_classe.jpg](./img/crc/EEbook.jpg)
![diagrammi_di_classe.jpg](./img/crc/EFeedback.jpg)
![diagrammi_di_classe.jpg](./img/crc/ELibro.jpg)
![diagrammi_di_classe.jpg](./img/crc/EPrenotazioni.jpg)
![diagrammi_di_classe.jpg](./img/crc/EPrestito.jpg)
![diagrammi_di_classe.jpg](./img/crc/ETessera.jpg)
![diagrammi_di_classe.jpg](./img/crc/EUtente.jpg)
![diagrammi_di_classe.jpg](./img/crc/EUtenteGamification.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIAmministrativa.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIAutenticazione.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIBiblioteca.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIGamification.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIPrestiOnline.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIPrestiti.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIRicerca.jpg)
![diagrammi_di_classe.jpg](./img/crc/UITesseramento.jpg)
![diagrammi_di_classe.jpg](./img/crc/UIUtente.jpg)

## 9. Diagrammi di Sequenza
![AU_1](./img/diagrammi_di_sequenza/AU_1.jpg)
![AU_2](./img/diagrammi_di_sequenza/AU_2.jpg)
![AU_3](./img/diagrammi_di_sequenza/AU_3.jpg)
![AU_4](./img/diagrammi_di_sequenza/AU_4.jpg)
![AU_5](./img/diagrammi_di_sequenza/AU_5.jpg)
![T_1](./img/diagrammi_di_sequenza/T_1.jpg)
![T_2](./img/diagrammi_di_sequenza/T_2.jpg)
![T_3](./img/diagrammi_di_sequenza/T_3.jpg)
![T_4](./img/diagrammi_di_sequenza/T_4.jpg)
![T_5](./img/diagrammi_di_sequenza/T_5.jpg)
![G_1](./img/diagrammi_di_sequenza/G_1.jpg)
![G_2](./img/diagrammi_di_sequenza/G_2.jpg)
![G_3](./img/diagrammi_di_sequenza/G_3.jpg)
![G_4](./img/diagrammi_di_sequenza/G_4.jpg)
![G_5](./img/diagrammi_di_sequenza/G_5.jpg)
![PL_1](./img/diagrammi_di_sequenza/PL_1.jpg)
![PL_2](./img/diagrammi_di_sequenza/PL_2.jpg)
![PL_3](./img/diagrammi_di_sequenza/PL_3.jpg)
![PL_4](./img/diagrammi_di_sequenza/PL_4.jpg)
![PS_1](./img/diagrammi_di_sequenza/PS_1.jpg)
![PS_2](./img/diagrammi_di_sequenza/PS_2.jpg)
![PS_3](./img/diagrammi_di_sequenza/PS_3.jpg)
![SA_1](./img/diagrammi_di_sequenza/SA_1.jpg)
![SA_2](./img/diagrammi_di_sequenza/SA_2.jpg)
![SA_3](./img/diagrammi_di_sequenza/SA_3.jpg)
![SA_4](./img/diagrammi_di_sequenza/SA_4.jpg)


## 10. Diagrammi Entità Relazione
![diagrammi_di_classe.jpg](./img/diagrammi_entita_realazione.jpg)
