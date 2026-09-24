# Recupero 24/09/2026 dal campus di Forli

L’`ingegneria del software` tratta la realizzazione di sistemi software (sw) di dimensioni e complessità talmente elevate da richiedere uno o più team di persone per la loro costruzione

"L’ingegneria del software è l’approccio sistematico allo sviluppo, all’operatività, alla manutenzione e al ritiro del software".
Il che vuol dire che c'e' un modo (una teoria) per fare il software (svilupparlo, operarlo, mantenerlo, ritirarlo).

"L’ingegneria del software è la disciplina tecnologica e manageriale che riguarda la produzione sistematica e la manutenzione dei prodotti software che vengono sviluppati e modificati `entro i tempi e i costi preventivati`"

"L’ingegneria del software è un corpus di teorie, metodi e strumenti, sia di tipo tecnologico che organizzativo, che consentono di produrre applicazioni con le desiderate caratteristiche di `qualità`"

## Qualita' del software

Le qualità su cui si basa la valutazione di un sw possono essere classificate in:
* `Interne`: riguardano le caratteristiche legate allo sviluppo del sw; non sono visibili agli utenti
* `Esterne`: riguardano le funzionalità fornite dal prodotto; sono visibili agli utenti

> [!WARNING]
> Queste due categorie sono strettamente collegate, infatti non e'
> possibile ottenere le qualita' esterne se il sw non gode delle interne.

Sono anche classificate in:
* `Relative al prodotto`: riguardano le caratteristiche stesse del sw e sono sempre valutabili
* `Relative al processo`: riguardano i metodi utilizzati durante lo sviluppo del sw

### Qualita'

* [Correttezza]: un sw è corretto se rispetta le specifiche di progetto;  -- _esterna, rel al prodotto_
* [Affidabilità]: un sw è affidabile se l’utente può dipendere da esso; -- _esterna, rel al prodotto_
* [Robustezza]: un sw è robusto se si comporta in modo ragionevole anche in circostanze non previste dalle specifiche di progetto (es. input incorretti, rotture di dischi); -- _esterna, rel al prodotto, rel al processo_
* [Efficienza]: un sw è efficiente se usa intelligentemente le risorse di calcolo; -- _esterna, rel al prodotto_
* [Facilità d’uso]: un sw è facile da usare se l’interfaccia che presenta all’utente gli permette di esprimersi in modo naturale -- _esterna rel al prodotto_
* [Verificabilità]: un sw è verificabile se le sue caratteristiche (correttezza, performance, ecc.) sono facilmente valutabili -- _interna, rel al prodotto, rel al processo_
* [Riusabilità]: un sw è riusabile se può essere usato, in tutto o in parte, per costruire nuovi sistemi -- _interna, rel al prodotto_
* [Portabilità]: un sw è portabile se può funzionare su più piattaforme (es. Java) -- _esterna, rel al prodotto_
* [Facilità di manutenzione]: un sw è facile da manutenere non solo se è strutturato in modo tale da facilitare la ricerca degli errori (`modifiche correttive`) ma anche se la sua struttura permette di aggiungere nuove funzionalità al sistema (`modifiche perfettive`) o di adattarlo ai cambiamenti del dominio applicativo (`modifiche adattative`) -- _interna, relativa al prodotto_
* [Interoperabilità]: fa riferimento all’abilità di un sistema di coesistere e cooperare con altri sistemi (es. un word processor in cui possono essere creati grafici) -- _esterna, rel al prodotto_
* [Produttività]: misura l’efficienza del processo di produzione del software in termini di velocità di consegna del sw; -- _rel processo_
* [Tempestività]: misura la capacità del processo di produzione del software di valutare e rispettare i tempi di consegna del prodotto; -- _rel al processo_
* [Trasparenza]: un processo di produzione del software si dice trasparente se permette di capire il suo stato attuale e tutti i suoi passi; -- _rel al processo_

## Ciclo di vita del software

1. Definizione strategica:
    Vengono prese decisioni sull’area aziendale che deve essere oggetto di automazione 
2. Pianificazione:
    Vengono definiti gli obiettivi, evidenziati i fabbisogni e viene condotto uno studio di fattibilità per individuare possibili strategie di attuazione e avere una prima idea dei `costi`, dei `benefici` e dei `tempi`. Deve portare ad individuare priorita' e interventi realizzabili.
3. Controllo di qualità:
    Viene predisposto un piano di controllo di qualità per il progetto, allo scopo di garantire il rispetto delle specifiche e di controllare che il sistema realizzato si comporti come previsto
4. Analisi dei requisiti:
    Formalizza i requisiti avvalendosi di tecniche di modellazione della realtà e produce macro-specifiche per la fase di progettazione
5. Progettazione del sistema:
    Interpreta i requisiti in una soluzione architetturale di massima. Produce specifiche indipendenti dai particolari strumenti che saranno usati per la costruzione del sistema
6. Progettazione esecutiva:
    Vengono descritti struttura e comportamento dei componenti dell’architettura, producendo specifiche che possano dar luogo, attraverso il ricorso a strumenti di sviluppo opportuni, a un prodotto funzionante
7. Realizzazione e collaudo in fabbrica:
    Il sistema viene implementato sulla piattaforma prescelta e viene testato internamente ( a-test) sulla base dei casi prova definiti durante la fase di analisi
8. Certificazione:
    L’attività di certificazione del software ha lo scopo di verificare che esso sia stato sviluppato secondo i criteri previsti dal metodo tecnico di progetto, in conformità alle specifiche di sistema e a tutta la documentazione di progetto
9. Installazione:
    Il sistema viene installato e configurato, e vengono recuperati gli eventuali dati pregressi 
10. Collaudo del sistema installato:
    Gli utenti testano “in vitro” il prodotto installato ( b-test). Si possono evidenziare errori bloccanti (malfunzionamenti che pregiudicano l’attività di collaudo), errori non bloccanti (malfunzionamenti che non pregiudicano l’attività di collaudo), problemi di operatività (una funzionalità richiesta non viene attuata adeguatamente) e funzionali (una funzionalità richiesta non è implementata)
11. Esercizio:
    Quando il collaudo dà esito positivo il sistema viene avviato (“messo in produzione”), inizialmente affiancando e poi sostituendo gradualmente l’eventuale sistema preesistente
12. Diagnosi:
    Durante l’esercizio gli utenti rilevano eventuali errori
13. Manutenzione:
    Gli errori che si manifestano durante il funzionamento vengono segnalati e corretti (manutenzione correttiva). Può inoltre essere necessario intervenire sul software per adattarlo ai cambiamenti del dominio applicativo (manutenzione adattativa)
14. Evoluzione:
    Si valutano le possibilità di far evolvere il sistema incorporando nuove funzionalità o migliorandone l’operatività (manutenzione evolutiva o perfettiva) 

### Definizione strategica e pianificazione (1 e 2)

L'idea è decidere, con un orizzonte anche di 3-5 anni, quali progetti informatici convenga realizzare considerando la situazione attuale e le risorse disponibili. Non vengono considerati soltanto aspetti informatici, ma anche informativi e organizzativi. Alla fine bisogna individuare le priorità e gli interventi concretamente realizzabili, valutandone anche i costi.

Quindi è una visione molto "manageriale":
Che cosa vorremmo fare?
        ↓
Quali risorse abbiamo?
        ↓
Quali progetti sono più importanti?
        ↓
Quanto costano?
        ↓
Quali realizziamo davvero?

### Studio di fattibilita' (2)

Lo studio di fattibilità parte quando esiste già un'idea abbastanza concreta: sappiamo quale problema vogliamo risolvere, l'area di intervento e almeno a grandi linee quale potrebbe essere il progetto.
Il suo scopo è fornire ai responsabili le informazioni necessarie per decidere se avviare effettivamente il progetto e quindi `effettuare l'investimento`.

Bisogna chiarire:
Perché lo facciamo?             → obiettivi
Chi/cosa riguarda?              → ambito e attori
Che vantaggi porterà?           → benefici attesi
Come sarà la soluzione?         → caratteristiche
Come sarà fatto grossomodo?     → progetto di massima
Quanto lavoro/costo richiede?   → stima impegno e costi
Quanto tempo richiede?          → tempi
Come verrà realizzato?          → modalità operative

3 tipi di fattibilita':
* Fattibilità tecnica:
    Esistono strumenti idonei? La proposta è realizzabile nell’ambito dell’organizzazione esistente? Il sistema sarà accettato e utilizzato? `"Siamo tecnicamente in grado di farlo?"`
* Fattibilità economica:
    I costi economici e le altre risorse necessarie per la realizzazione sono giustificati dai benefici attesi?
* Fattibilità temporale:
    La realizzabilità si può concretizzare in tempi “accettabili” (rispetto ai quali il sistema continua ad essere utile)?

Serve a rendere più consapevoli le decisioni di investimento, confrontare costi e benefici, ridurre l'incertezza e i rischi e trasformare una semplice idea in un progetto sufficientemente concreto da poter entrare nella fase di realizzazione.

### Analisi dei requisiti

Ancora prima di iniziare devo chiedermi:
`Cosa deve fare il sistema?`
Lo scopo è produrre un documento di specifica dei requisiti che diventerà l’input delle successive fasi di progettazione e realizzazione.

DIO BO CHE DUE COJONI STA MATERIA, LA CONTINUO UN ALTRA VOLTA.

# 18/09/2026

"travaso di bile"

## Qualita' del software

Dai ti ricordi:
* Analisi: descrivere il dominio e cio' che il software deve fare;
    * Analisi orientata agli oggetti (`statica`)
    * Analisi orientata alle funzioni (`funzionale`)
    * Analisi orientata agli stati (`dinamica`)
* Progettazione

Il problema e' che nei domini di solito le funzionalita' richieste cambiano spesso (invece gli oggetti che li compongono di solito rimangono sempre gli stessi).
Ecco perche' non ti conviene basarsi su un analisi orientata alle funzioni per fare un software... probabilmente meglio orientarsi agli oggetti.

---

# Analisi

### Analisi orientata agli oggetti (modellazione statica)

Identifico il mio dominio modellandone gli oggetti e le interazioni tra loro.
L'analisi statica e' descrivere i concetti che appartengono al dominio di appartenenza e come interagiscono tra loro, si creano dei grafici che sembrano la fusione tra UML e ER

* Killer application sono i database (non a caso l'ER e' proprio modellazione statica)

### Analisi orientata alle funzioni (modellazione funzionale)

Si modella, spiega il software in termini di funzionalita'.
...
Gerarchia: e' un albero (tipo le gerarchie in basi di dati), in cui vale la relazione "is a" ma anche "part of", soprattutto quest'ultima in questo ambito.
Infatti ogni funzione e' composta da sottofunzioni sempre piu' specializzate.
Quindi si creano prima gli alberi che poi saranno implementati con funzioni (procedure)

Ho un input e voglio un output:
* Killer application tipo un compilatore, dai il codice sorgente, segue un algoritmo che sputa fuori il codice macchina.

### Analisi orientata agli stati (modellazione dinamica)

Si studiano gli stati che possono assumere le entita' del dominio.
Una persone puo' essere sposato, single, celibe, avvocato, ...
Si descrivono anche le modalita' con cui un entita' passa da uno stato a un altro.
Una persona passa da celibe a sposato via un matrimonio.

* Ad esempio uno scheduler di un OS, un interfaccia utente di qualche programma


## Meccanismi di Astrazione

Ci sono diversi livelli di dettaglio in cui si arrivano a fare questi 3 tipi di analisi.
Puoi fare una analisi ad oggetti piu' o meno dettagliata.

### Classificazione

La classificazione consente di raggruppare in classi oggetti, funzioni, o stati in base alle loro proprietà.
Es: persone basse o alte.
* Sono le `entita'` del diagramma ER.

### Generalizzazione (specializzazione)

Come le gerarchie in basi di dati: gerarchia "is a".
Studente e docente sono Persone (sono sottoinsiemi di persona).
* Sono le `gerarchie` del diagramma ER.

### Aggregazione

Un oggetto puo' essere composto da altri oggetti.
Una macchina e' fatta da ruote, motore, volante, ...
* Sono le `relazioni` del diagramma ER (con scritto "e' parte di").

### Associazioni

Oltre ai meccanismi citati è importante modellare le associazioni che sussistono fra le varie classi
Diverse persone possono lavorare per diverse aziende.


## Linguaggi per la specifica dei requisiti

### Linguaggi informali

Il linguaggio naturale, alla base della comunicazione durante le interviste tra analista e utente, non può essere adottato come unico mezzo per produrre documenti di specifica per le innumerevoli ambiguità di significato.
Troppo ambigui, non si possono usare.

### Linguaggi semiformali

notazione grafica, che presenta una semantica sfumata, accoppiata con descrizioni in
linguaggio naturale (esempi : E/R, DFD)
"In medio stat virtus", infatti usiamo questi.

### Linguaggi formali

linguaggi di specifica basati sulla logica dei predicati
linguaggi di specifica algebrici
linguaggi concettuali per basi di dati
Troppo complicati, non ne vale la pena.

---

# Progettazione

Se analisi era "cosa devo fare", ora pensiamo a "come lo faccio".

Il software dovrebbe avere certe qualita': affidabilita', modificabilita', comprensibilita', riusabilita'.
Queste qualita' sono importanti per avere un codice ben manutenibile (infatti la manutenzione e' la cosa piu' costosa nel ciclo di vita di un software).

## Principi fondanti della progettazione

* `Formalita'`: Prima di fare lo schema relazionale fai lo schema ER. Si usano formalismi per la specifica dei requisiti.

* `Anticipazione dei Cambiamenti`: Esempio del millennium bug, se sono nel 1998 che scrivo un software uso 4 cifre per l'anno invece che solo 2 (cosi' potro' distinguere l'anno quando arrivera' il 2000).
Oppure una azienda mi chiede un software per 100 clienti ma io prevedo che i clienti aumenteranno e allora la progetto anche per 1000.
Ovviamente puoi anticipare fino a un certo punto

* `Separazione degli argomenti`: Divide et impera.
    * Tempo -> la fai per forza, prima fai un analisi, poi fai la progettazione, ... NON TUTTO INSIEME (una cosa alla volta)
    * Livello di qualita' -> prima scrivo del software corretto poi lo faccio piu' efficiente.
    * Livello di astrazione -> inizio ad alto livello e poi scendo man mano nello sviluppo.
    * Vista ->
    * Dimensione -> modularizzazione (non software monolitico gigantesco, moduli che fanno cose diverse)

## Separazione degli argomenti
### Modularita'

Con il termine modulo si indica il componente di base di un sistema software che raccoglie un insieme di funzionalità tra loro strettamente legate.
Ciascun modulo rimane separato dagli altri. Comunicano tra loro attraverso interfaccie.
Cosi' e' anche piu' facile capire che cosa fa un software: guardi prima cosa fanno i moduli e poi vedi come comunicano.
Non ho bisogno di sapere le implementazioni del modulo, rimango a ragionare sulle interfacce, vedo le funzionalita' offerte dai moduli, cosa vogliono in input e cosa restituiscono in output.

### Astrazione

### Generalizzazione

Ho un problema, magari c'e' un problema simile piu' generale che pero' ha gia' una soluzione.
Ad esempio i design pattern. Risolvono dei problemi noti in modo efficiente e si sa che vanno bene.

---

