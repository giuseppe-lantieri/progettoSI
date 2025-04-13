# Documento di Analisi – Gestione Biblioteche Romane

## 1. Introduzione
In questo documento viene descritta l’analisi del sistema per la gestione delle biblioteche romane. Il testo si articola in diverse sezioni:  
- Una descrizione preliminare del sistema;  
- L’analisi dei casi d’uso e la definizione del glossario;  
- L’estrazione delle classi di analisi tramite le schede CRC;  
- La rappresentazione delle relazioni mediante diagrammi EBC;  
- I diagrammi di sequenza.

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
L’approccio “nomi-verbi” prevede di identificare le entità principali (nomi) e le azioni (verbi) che il sistema deve supportare. Di seguito sono elencate alcune delle principali entità e operazioni, estratte dall’analisi dei casi d’uso.

### 4.1 Entità (Nomi)
- **Utente**: astrazione che rappresenta l’Utente autenticato.
- **Bibliotecario**: utente con privilegi amministrativi.
- **Libro**: oggetto ricercabile, disponibile o meno per il prestito.
- **Prestito**: operazione relativa al prestito fisico o digitale(o ebook) dei libri.
- **Tessera**: strumento di identificazione che consente l’accesso a privilegi particolari.
- **Prenotazione**: richiesta di utilizzo di uno spazio comune.
- **Commento/Recensione**: feedback lasciato dagli utenti all’interno della sezione di gamification.
- **Biblioteca**: rappresentazione dell’istituzione, per la pubblicazione di notizie e la gestione degli spazi.

### 4.2 Azioni (Verbi)
Le principali operazioni individuate sono:
- **Autenticare**: gestioje dell’accesso al sistema (AU_1, AU_2).
- **Registrare**: inserimento di nuovi utenti (AU_4).
- **Modificare**: aggiornamento di password (AU_3) o profili (G_2).
- **Effettuare Logout**: terminare una sessione (AU_5).
- **Richiedere Tessera**: gestione delle operazioni di tesseramento (T_1, T_2, T_3, T_4, T_5).
- **Partecipare**: iscrizione al sistema di gamification (G_1).
- **Commentare/Recensire**: inserimento di feedback sui libri (G_3).
- **Segnalare**: gestione di problematiche (G_4, PS_3).
- **Riscattare**: riscatto dei punti (G_5).
- **Ricercare**: ricerca di libri e richiesta di prestito (PL_1).
- **Restituire**: restituzione di libri (PL_2).
- **Richiedere Allungamento**: estensione del periodo di prestito (PL_3).
- **Richiedere e-book**: ottenimento di prestito digitale (PL_4).
- **Prenotare/Cancellare Prenotazione**: gestione delle prenotazioni degli spazi (PS_1, PS_2).
- **Caricare**: inserimento di nuovi libri nel sistema (SA_1).
- **Segnalare Prestito e Notizie**: aggiornamento dello stato del sistema (SA_2, SA_3).
- **Gestire**: personalizzazione della pagina della biblioteca (SA_4).

<div style="page-break-after: always;"></div>

## 5. Diagrammi di Attività

**AU_1**: Autenticazione Utente Sistema Interno  
![AU_1](./img/diagrammi_di_attivita/AU_1.jpg)

<div style="page-break-after: always;"></div>

**AU_2**: Autenticazione Utente Tramite Sistema Esterno  
![AU_2](./img/diagrammi_di_attivita/AU_2.jpg)

<div style="page-break-after: always;"></div>

**AU_3**: Modifica Password Sistema Interno  
![AU_3](./img/diagrammi_di_attivita/AU_3.jpg)

<div style="page-break-after: always;"></div>

**AU_4**: Registrazione  
![AU_4](./img/diagrammi_di_attivita/AU_4.jpg)

<div style="page-break-after: always;"></div>

**AU_5**: Logout
![AU_5](./img/diagrammi_di_attivita/AU_5.jpg)

<div style="page-break-after: always;"></div>

**T_1**: Nuovo Tesseramento  
![T_1](./img/diagrammi_di_attivita/T_1.jpg)

<div style="page-break-after: always;"></div>

**T_2**: Rinnovo Tesseramento  
![T_2](./img/diagrammi_di_attivita/T_2.jpg)

<div style="page-break-after: always;"></div>

**T_3**: Cancellazione Tesseramento  
![T_3](./img/diagrammi_di_attivita/T_3.jpg)

<div style="page-break-after: always;"></div>

**T_4**: Denuncia Smarrimento Tesseramento  
![T_4](./img/diagrammi_di_attivita/T_4.jpg)

<div style="page-break-after: always;"></div>

**T_5**: Denuncia Furto Tesseramento
![T_5](./img/diagrammi_di_attivita/T_5.jpg)

<div style="page-break-after: always;"></div>

**G_1**: Partecipazione al Sistema di Gamification  
![G_1](./img/diagrammi_di_attivita/G_1.jpg)

<div style="page-break-after: always;"></div>

**G_2**: Gestione Profilo  
![G_2](./img/diagrammi_di_attivita/G_2.jpg)

<div style="page-break-after: always;"></div>

**G_3**: Inserimento Commento/Recensione  
![G_3](./img/diagrammi_di_attivita/G_3.jpg)

<div style="page-break-after: always;"></div>

**G_4**: Segnalazione Commento/Recensione  
![G_4](./img/diagrammi_di_attivita/G_4.jpg)

<div style="page-break-after: always;"></div>

**G_5**: Riscatto Punti
![G_5](./img/diagrammi_di_attivita/G_5.jpg)

<div style="page-break-after: always;"></div>

**PL_1**: Ricerca Libro Fisico e Richiesta di Prestito  
![PL_1](./img/diagrammi_di_attivita/PL_1.jpg)

<div style="page-break-after: always;"></div>

**PL_2**: Restituzione Prestito Fisico  
![PL_2](./img/diagrammi_di_attivita/PL_2.jpg)

<div style="page-break-after: always;"></div>

**PL_3**: Richiesta Allungamento Prestito Fisico  
![PL_3](./img/diagrammi_di_attivita/PL_3.jpg)

<div style="page-break-after: always;"></div>

**PL_4**: Richiesta E-book
![PL_4](./img/diagrammi_di_attivita/PL_4.jpg)

<div style="page-break-after: always;"></div>

**PS_1**: Prenotazione di uno Spazio Comune  
![PS_1](./img/diagrammi_di_attivita/PS_1.jpg)

<div style="page-break-after: always;"></div>

**PS_2**: Cancellazione di una Prenotazione  
![PS_2](./img/diagrammi_di_attivita/PS_2.jpg)

<div style="page-break-after: always;"></div>

**SA_1**: Caricamento Nuovi Libri  

![SA_1](./img/diagrammi_di_attivita/SA_1.jpg)
<div style="page-break-after: always;"></div>

**SA_2**: Segnalazione Prestito Avvenuto Dal Vivo  
![SA_2](./img/diagrammi_di_attivita/SA_2.jpg)

<div style="page-break-after: always;"></div>

**SA_3**: Segnalazione Notizie  
![SA_3](./img/diagrammi_di_attivita/SA_3.jpg)

<div style="page-break-after: always;"></div>

**SA_4**: Gestione Pagina della Biblioteca
![SA_4](./img/diagrammi_di_attivita/SA_4.jpg)

<div style="page-break-after: always;"></div>

## 6. Diagrammi di Classe
![diagrammi_di_classe.jpg](./img/diagrammi_di_classe.jpg)

<div style="page-break-after: always;"></div>

## 7. Diagrammi di Package
![diagrammi_di_classe.jpg](./img/diagrammi_package.jpg)

<div style="page-break-after: always;"></div>


## 8. Schede CRC
### CAmministrativo
![diagrammi_di_classe.jpg](./img/crc/CAmministrativo.jpg)

<div style="page-break-after: always;"></div>

### CEbook
![diagrammi_di_classe.jpg](./img/crc/CEbook.jpg)

<div style="page-break-after: always;"></div>

### CGamification
![diagrammi_di_classe.jpg](./img/crc/CGamification.jpg)

<div style="page-break-after: always;"></div>

### CPagineSito
![diagrammi_di_classe.jpg](./img/crc/CPagineSito.jpg)

<div style="page-break-after: always;"></div>

### CPrenotazione
![diagrammi_di_classe.jpg](./img/crc/CPrenotazione.jpg)

<div style="page-break-after: always;"></div>

### CPrestiti
![diagrammi_di_classe.jpg](./img/crc/CPrestiti.jpg)

<div style="page-break-after: always;"></div>

### CRicerche
![diagrammi_di_classe.jpg](./img/crc/CRicerche.jpg)

<div style="page-break-after: always;"></div>

### CServiziEsterni
![diagrammi_di_classe.jpg](./img/crc/CServiziEsterni.jpg)

<div style="page-break-after: always;"></div>

### CTesseramento
![diagrammi_di_classe.jpg](./img/crc/CTesseramento.jpg)

<div style="page-break-after: always;"></div>

### CUtenza
![diagrammi_di_classe.jpg](./img/crc/CUtenza.jpg)

<div style="page-break-after: always;"></div>

### EBiblioteca
![diagrammi_di_classe.jpg](./img/crc/EBiblioteca.jpg)

<div style="page-break-after: always;"></div>

### EBibliotecario
![diagrammi_di_classe.jpg](./img/crc/EBibliotecario.jpg)

<div style="page-break-after: always;"></div>

### EEbook
![diagrammi_di_classe.jpg](./img/crc/EEbook.jpg)

<div style="page-break-after: always;"></div>

### EFeedback
![diagrammi_di_classe.jpg](./img/crc/EFeedback.jpg)

<div style="page-break-after: always;"></div>

### ELibro
![diagrammi_di_classe.jpg](./img/crc/ELibro.jpg)

<div style="page-break-after: always;"></div>

### EPrenotazioni
![diagrammi_di_classe.jpg](./img/crc/EPrenotazioni.jpg)

<div style="page-break-after: always;"></div>

### EPrestito
![diagrammi_di_classe.jpg](./img/crc/EPrestito.jpg)

<div style="page-break-after: always;"></div>

### ETessera
![diagrammi_di_classe.jpg](./img/crc/ETessera.jpg)

<div style="page-break-after: always;"></div>

### EUtente
![diagrammi_di_classe.jpg](./img/crc/EUtente.jpg)

<div style="page-break-after: always;"></div>

### EUtenteGamification
![diagrammi_di_classe.jpg](./img/crc/EUtenteGamification.jpg)

<div style="page-break-after: always;"></div>

### UIAmministrativa
![diagrammi_di_classe.jpg](./img/crc/UIAmministrativa.jpg)

<div style="page-break-after: always;"></div>

### UIAutenticazione
![diagrammi_di_classe.jpg](./img/crc/UIAutenticazione.jpg)

<div style="page-break-after: always;"></div>

### UIBiblioteca
![diagrammi_di_classe.jpg](./img/crc/UIBiblioteca.jpg)

<div style="page-break-after: always;"></div>

### UIGamification
![diagrammi_di_classe.jpg](./img/crc/UIGamification.jpg)

<div style="page-break-after: always;"></div>

### UIPrestiOnline
![diagrammi_di_classe.jpg](./img/crc/UIPrestiOnline.jpg)

<div style="page-break-after: always;"></div>

### UIPrestiti
![diagrammi_di_classe.jpg](./img/crc/UIPrestiti.jpg)

<div style="page-break-after: always;"></div>

### UIRicerca
![diagrammi_di_classe.jpg](./img/crc/UIRicerca.jpg)

<div style="page-break-after: always;"></div>

### UITesseramento
![diagrammi_di_classe.jpg](./img/crc/UITesseramento.jpg)

<div style="page-break-after: always;"></div>

### UIUtente
![diagrammi_di_classe.jpg](./img/crc/UIUtente.jpg)

<div style="page-break-after: always;"></div>


## 9. Diagrammi di Sequenza
**AU_1**: Autenticazione Utente Sistema Interno  
![AU_1](./img/diagrammi_di_sequenza/AU_1.jpg)

<div style="page-break-after: always;"></div>

**AU_2**: Autenticazione Utente Tramite Sistema Esterno  
![AU_2](./img/diagrammi_di_sequenza/AU_2.jpg)

<div style="page-break-after: always;"></div>

**AU_3**: Modifica Password Sistema Interno  
![AU_3](./img/diagrammi_di_sequenza/AU_3.jpg)

<div style="page-break-after: always;"></div>

**AU_4**: Registrazione  
![AU_4](./img/diagrammi_di_sequenza/AU_4.jpg)

<div style="page-break-after: always;"></div>

**AU_5**: Logout
![AU_5](./img/diagrammi_di_sequenza/AU_5.jpg)

<div style="page-break-after: always;"></div>

**T_1**: Nuovo Tesseramento  
![T_1](./img/diagrammi_di_sequenza/T_1.jpg)

<div style="page-break-after: always;"></div>

**T_2**: Rinnovo Tesseramento  
![T_2](./img/diagrammi_di_sequenza/T_2.jpg)

<div style="page-break-after: always;"></div>

**T_3**: Cancellazione Tesseramento  
![T_3](./img/diagrammi_di_sequenza/T_3.jpg)

<div style="page-break-after: always;"></div>

**T_4**: Denuncia Smarrimento Tesseramento  
![T_4](./img/diagrammi_di_sequenza/T_4.jpg)

<div style="page-break-after: always;"></div>

**T_5**: Denuncia Furto Tesseramento
![T_5](./img/diagrammi_di_sequenza/T_5.jpg)

<div style="page-break-after: always;"></div>

**G_1**: Partecipazione al Sistema di Gamification  
![G_1](./img/diagrammi_di_sequenza/G_1.jpg)

<div style="page-break-after: always;"></div>

**G_2**: Gestione Profilo  
![G_2](./img/diagrammi_di_sequenza/G_2.jpg)

<div style="page-break-after: always;"></div>

**G_3**: Inserimento Commento/Recensione  
![G_3](./img/diagrammi_di_sequenza/G_3.jpg)

<div style="page-break-after: always;"></div>

**G_4**: Segnalazione Commento/Recensione  
![G_4](./img/diagrammi_di_sequenza/G_4.jpg)

<div style="page-break-after: always;"></div>

**G_5**: Riscatto Punti
![G_5](./img/diagrammi_di_sequenza/G_5.jpg)

<div style="page-break-after: always;"></div>

**PL_1**: Ricerca Libro Fisico e Richiesta di Prestito  
![PL_1](./img/diagrammi_di_sequenza/PL_1.jpg)

<div style="page-break-after: always;"></div>

**PL_2**: Restituzione Prestito Fisico  
![PL_2](./img/diagrammi_di_sequenza/PL_2.jpg)

<div style="page-break-after: always;"></div>

**PL_3**: Richiesta Allungamento Prestito Fisico  
![PL_3](./img/diagrammi_di_sequenza/PL_3.jpg)

<div style="page-break-after: always;"></div>

**PL_4**: Richiesta E-book
![PL_4](./img/diagrammi_di_sequenza/PL_4.jpg)

<div style="page-break-after: always;"></div>

**PS_1**: Prenotazione di uno Spazio Comune  
![PS_1](./img/diagrammi_di_sequenza/PS_1.jpg)

<div style="page-break-after: always;"></div>

**PS_2**: Cancellazione di una Prenotazione  
![PS_2](./img/diagrammi_di_sequenza/PS_2.jpg)

<div style="page-break-after: always;"></div>

**SA_1**: Caricamento Nuovi Libri  
![SA_1](./img/diagrammi_di_sequenza/SA_1.jpg)

<div style="page-break-after: always;"></div>

**SA_2**: Segnalazione Prestito Avvenuto Dal Vivo  
![SA_2](./img/diagrammi_di_sequenza/SA_2.jpg)

<div style="page-break-after: always;"></div>

**SA_3**: Segnalazione Notizie  
![SA_3](./img/diagrammi_di_sequenza/SA_3.jpg)

<div style="page-break-after: always;"></div>

**SA_4**: Gestione Pagina della Biblioteca
![SA_4](./img/diagrammi_di_sequenza/SA_4.jpg)

<div style="page-break-after: always;"></div>


## 10. Diagrammi Entità Relazione
![diagrammi_di_classe.jpg](./img/diagrammi_entita_relazione.jpg)
