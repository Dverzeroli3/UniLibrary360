\# Project Plan — UniLibrary360



| Versione | Data | Autore | Modifiche |

| :--- | :--- | :--- | :--- |

| 1.0.0 | 17/11/2026 | Team UniLibrary360 | Versione iniziale del Project Plan |



\---



\## 1. Introduction

\*\*UniLibrary360\*\* è un sistema software in linguaggio Java progettato per digitalizzare e automatizzare la gestione operativa di una biblioteca universitaria.

Il sistema consente agli utenti registrati (Studenti e Docenti) di consultare il catalogo, prenotare libri non disponibili e monitorare i propri prestiti e le eventuali sanzioni. Consente inoltre al personale bibliotecario di gestire l'inventario (libri e copie fisiche), registrare prestiti e restituzioni, gestire le code di prenotazione e applicare le sanzioni per ritardi o danneggiamenti.

L'obiettivo del progetto è applicare in modo rigoroso le metodologie di Ingegneria del Software (requisiti, modellazione UML, design pattern, testing e configuration management), dedicando circa il 70% dell'impegno ad analisi e progettazione e il 30% a implementazione e verifica.



\## 2. Process model

Il team adotta un modello di sviluppo \*\*Iterativo e Incrementale\*\* (ispirato a Scrum, con iterazioni settimanali/bisettimanali).

\* \*\*Motivazione:\*\* Permette di consolidare l'analisi dei requisiti e i diagrammi UML nelle prime settimane, per poi sviluppare e testare il software per incrementi funzionali, riducendo il rischio di errori architetturali tardivi.



\## 3. Organization 

Il gruppo è composto da 3 studenti con organizzazione \*\*paritaria (Agile/Democratica)\*\*: tutti i membri partecipano attivamente a requisiti, modellazione UML, sviluppo Java e testing, garantendo un contributo equo e tracciabile su GitHub. Per coordinare efficacemente le attività, ciascun membro funge da referente principale per un'area specifica:

\* \*\*Daniel Verzeroli (Matricola: 1099658) — Referente Architettura \& Sviluppo Core:\*\* Coordinamento del Class Diagram, generazione codice da StarUML, struttura dei package e implementazione dei Design Pattern.

\* \*\*Lorenzo Raineri (1099841) — Referente Requisiti \& Modellazione Comportamentale:\*\* Redazione specifica dei requisiti (IEEE 830), Use Case, State Machine, Sequence e Activity Diagram.

\* \*\*Federico Raineri (1099840) — Referente QA, Persistenza \& Testing:\*\* Setup progetto Eclipse/Maven, configurazione database embedded, suite di test JUnit e analisi statica del codice.



\## 4. Standards, guidelines, procedures

\* \*\*Codice Java:\*\* Convenzioni standard Oracle (CamelCase per classi e metodi, nomi significativi, incapsulamento tramite visibilità `private`/`protected`, documentazione Javadoc sulle classi e sui metodi pubblici). Nessun percorso assoluto nei riferimenti ai file.

\* \*\*Modellazione UML:\*\* Utilizzo esclusivo di \*\*StarUML 5\*\* con salvataggio del file sorgente `.mdj` nella cartella `documenti/`.

\* \*\*Struttura Repository GitHub:\*\* Separazione netta tra `documenti/` e `codice/`. Il progetto Eclipse/Maven è nominato con prefisso identificativo `UL360\_UniLibrary`. File `.gitignore` configurato per escludere `target/` e `.class`, mantenendo tracciati `.project`, `.classpath` e `pom.xml`.

\* \*\*Workflow Git:\*\* Sviluppo su branch dedicati (`docs/...`, `feature/...`, `fix/...`), apertura di \*Pull Request\* verso `main` con revisione obbligatoria di almeno un altro membro prima del merge, tracciamento dei task tramite \*GitHub Issues\*.



\## 5. Management activities

\* \*\*Allineamento settimanale:\*\* Riunione di 45-60 minuti ogni settimana per verificare lo stato delle milestone, risolvere blocchi tecnici e pianificare i task dell'iterazione successiva.

\* \*\*Tracciamento avanzamento:\*\* Utilizzo di una bacheca Kanban su \*GitHub Projects\* collegata alle \*Issue\* (colonne: \*To Do\*, \*In Progress\*, \*In Review\*, \*Done\*).



\## 6. Risks Potential



| Rischio | Probabilità | Impatto | Strategia di Mitigazione |

| :--- | :--- | :--- | :--- |

| Sottostima dei tempi di modellazione UML e documentazione | Media | Alto | Dedicare integralmente le settimane 2 e 3 ad analisi e UML prima di scrivere la logica applicativa. |

| Conflitti di merge o problemi di importazione progetto Eclipse/Maven | Media | Medio | Adottare branch separati per feature, definire subito l'architettura dei package e verificare l'importazione su tutti i PC. |

| Disallineamento tra diagrammi UML e codice implementato | Media | Alto | Generare lo scheletro delle classi da StarUML e aggiornare i diagrammi durante le revisioni pre-consegna. |

| Indisponibilità temporanea di un componente (esami/imprevisti) | Bassa | Alto | Condivisione continua del codice tramite commit frequenti e conoscenza trasversale di tutti i moduli. |



\## 7. Staffing

Il team è formato da tre studenti del corso di Ingegneria del Software dell'Università degli Studi di Bergamo:

1\. \*\*Daniel Verzeroli\*\* (Matr. 1099658)

2\. \*\*Lorenzo Raineri\*\* (Matr. 1099841)

3\. \*\*Federico Raineri\*\* (Matr. 1099840)



Tutti i membri possiedono conoscenze di base di programmazione ad oggetti in Java, basi di dati relazionali (SQL) e controllo versione con Git.



\## 8. Methods and techniques

\* \*\*IDE e Build:\*\* Eclipse IDE, Apache Maven per la gestione delle dipendenze (`JUnit 5`, `Log4j2`, database embedded `H2`).

\* \*\*Modellazione e MDA:\*\* StarUML v5 per tutti i diagrammi UML richiesti e generazione iniziale delle classi Java dal Class Diagram.

\* \*\*Design Pattern:\*\* Applicazione dei pattern \*Strategy\* (calcolo durata prestiti e sanzioni differenziate tra Studenti e Docenti), \*Observer\* (notifica automatica disponibilità copie prenotate) e \*State\* (gestione transizioni di stato di Copie e Prenotazioni).

\* \*\*Analisi Statica:\*\* Utilizzo di plugin Eclipse (SonarLint / PMD) per il controllo della qualità del codice e dell'assenza di cicli tra package.



\## 9. Quality assurance

\* \*\*Code Review:\*\* Ogni Pull Request deve essere revisionata da almeno un compagno per verificare aderenza ai requisiti, leggibilità e rispetto dell'architettura a livelli.

\* \*\*Testing:\*\* Sviluppo di test unitari JUnit in `src/test/java` per tutte le classi di dominio e i servizi principali, puntando a una code coverage superiore al 75%.

\* \*\*Metriche:\*\* Misurazione della complessità ciclomatica (McCabe) e verifica dell'assenza di dipendenze cicliche tra package prima del rilascio finale.



\## 10. Resources

\* \*\*Hardware:\*\* 3 PC personali dei componenti del team.

\* \*\*Software e Servizi:\*\* GitHub (repository privato condiviso con `garganti` e `silviabonfanti`), Eclipse IDE for Java Developers, JDK 17+, Apache Maven, StarUML v5. Tutti gli strumenti sono gratuiti/open-source.



\## 11. Budget and schedule

L'impegno complessivo stimato è di \*\*105 ore totali\*\* (\*\*35 ore a testa\*\*), ripartite in \*\*\~25 ore/testa (71%)\*\* per requisiti, modellazione e documentazione e \*\*\~10 ore/testa (29%)\*\* per implementazione e testing.



\### Cronoprogramma (Appello del 14/01/2027)



| Fase / Milestone | Periodo | Attività Principali | Deliverable / Verifica |

| :--- | :--- | :--- | :--- |

| \*\*M1: Setup \& Planning\*\* | 17/11/2026 – 27/11/2026 | Creazione repo GitHub, setup Maven/Eclipse, redazione Project Plan | `Project\_Plan.md` + apertura Issue al docente (entro 14/12) |

| \*\*M2: Requisiti \& Qualità\*\* | 28/11/2026 – 06/12/2026 | Elicitazione requisiti (IEEE 830), attributi qualità, Use Case Diagram | Documento 3 (Requisiti) + Use Case su StarUML |

| \*\*M3: Architettura \& UML\*\* | 07/12/2026 – 20/12/2026 | Class, Sequence, State Machine, Activity, Timing/Comm, Component e Package Diagram | Documento 4 (Design) + file `.mdj` StarUML |

| \*\*M4: Sviluppo Core \& DB\*\* | 21/12/2026 – 02/01/2027 | Generazione codice da UML, implementazione model, DAO (DB embedded), service e pattern | Codice sorgente funzionante su branch `main` |

| \*\*M5: UI, Testing \& Refactoring\*\* | 03/01/2027 – 09/01/2027 | Completamento UI, test JUnit, code coverage, metriche, refactoring e relazione | Congelamento codice (5 gg prima dell'orale) |

| \*\*M6: Rifinitura \& Presentazione\*\* | 10/01/2027 – 14/01/2027 | Revisione finale dei 6 documenti, preparazione slide da template e prova demo | Esame orale e discussione progetto (14/01/2027) |



\## 12. Changes

Qualsiasi modifica ai requisiti, all'architettura o alle scadenze interne verrà gestita tramite l'apertura di una specifica \*Issue\* su GitHub, discussa collegialmente dal team e documentata aggiornando la tabella delle versioni in testa ai documenti interessati (e nel Documento 2 - Gestione del Progetto).



\## 13. Delivery

Tutti i deliverable saranno rilasciati nel repository GitHub condiviso con i docenti secondo la seguente struttura:

\* \*\*`documenti/`:\*\*

&#x20; \* File sorgente StarUML (`UniLibrary360.mdj`).

&#x20; \* Relazione finale suddivisa nei 6 documenti richiesti (1. \*Project Plan\*, 2. \*Gestione del Progetto\*, 3. \*Requisiti\*, 4. \*Design\*, 5. \*Testing\*, 6. \*Maintenance\*).

&#x20; \* Presentazione per la discussione orale (basata sul template fornito dai docenti).

\* \*\*`codice/`:\*\*

&#x20; \* Progetto Eclipse/Maven `UL360\_UniLibrary` completo di sorgenti (`src/main/java`), test unitari (`src/test/java`), file `pom.xml`, script/file di inizializzazione del DB embedded e file di configurazione Eclipse (`.project`, `.classpath`).

