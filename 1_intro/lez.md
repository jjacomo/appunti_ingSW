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

# Il paradigma a Oggetti

_Un oggetto è un individuo sostanziale che possiede un identità e un insieme di proprietà, che ne rappresentano lo stato e il comportamento_.
Un'oggetto non e' una classe. E' composto da attributi che ad ogni istante ne definiscono lo `stato` (analisi orientata agli stati), funzionalita' (dicono cosa puo' fare l'oggetto) e un identificatore (OID, object identifier).

I concetti fondamentali:
* oggetto
* astrazione
* classe
* incapsulamento
* ereditarietà
* polimorfismo - late binding
* delegazione

# 22/09/2026

* Ogni operazione dichiarata da un oggetto specifica il nome dell’operazione, gli oggetti che prende come parametri e il valore restituito (signature)
* L’oggetto su cui l’operazione opera è definito implicitamente
* L’insieme di tutte le signature delle operazioni di un oggetto sono dette interfaccia dell’oggetto
    * L’interfaccia specifica l’insieme completo di tutte le richieste che possono essere inviate all’oggetto

Per passare da una interfaccia (signature) a una classe ci vogliono le `implementazioni` (metodi).

tipo e supertipo (p6)

`Astrazione dello stato` = calcolare un dato derviato a partire dallo stato di un oggetto.

Partendo dai tipi di dati astratti e implementandoli ottengo una classe.

> Un oggetto è sempre istanza di esattamente una classe

Qual'e' un operazioen che restituisce un astrazione di uno stato, ad esempio in una classe persona:
Tipo isMaggiorenne: calcola l'eta' a partire dalla data di nascita e vede se e' >18.

Sostenere un esame non cambia lo stato, fa un astrazione (?), lo studente viene collegato all'oggetto esame che ha sostenuto 

## Principio di Incapsulamento

Information hiding.
Lo stato di un oggetto e' nascosto al suo interno (non puoi mettere getter e setter altrimenti e' inutile).
L'unico modo per accedere all'oggetto si fa attraverso un interfaccia.
Attributi privati (lo so che in teoria si puo' mettere anche public ma sono linguaggi object oriented non object based).

* I dettagli dell’implementazione di una classe sono privati, cioè manipolabili direttamente solo dai metodi della classe e quindi protetti
* L’accesso dall’esterno agli attributi della classe avviene attraverso una ristretta interfaccia pubblica, costituita da un sottoinsieme dei metodi della classe
* Un oggetto esegue una operazione quando riceve una richiesta (messaggio) da un oggetto client

### Vantaggi
Proibisci di modificare direttamente lo stato dell'oggetto dall'esterno, definisci tu i modi per modificare il tuo oggetto (cosi' eviti anche che ci siano casini).
Cosi' mi da la non dipendenza dai dettagli implementativi che possono cambiare (l'interfaccia).

Ha anche lo svantaggio di essere un po' piu' difficile l'implementazione(?).

## Operazioni e metodi

Operazioni: signatures
Metodi: implementazione

I metodi possono essere classificati in:
* costruttori, per costruire oggetti a partire da parametri di ingresso restituendo l’OID dell’oggetto costruito. E' consigliato avercelo sempre cosi' da costrurire ogi volta un oggetto che abbia sempre una identita' sostanziale (e' meglio non avere un oggetto indefinito per cui ho solo allocato dello spazio).
* distruttori, per cancellare gli oggetti ed eventuali altri oggetti ad essi collegati (in java non esiste veramente, c'e' il garbage collector)
* accessori, per restituire informazioni sul contenuto degli oggetti (proprietà derivate)
* trasformatori, per modificare lo stato degli oggetti e di eventuali altri oggetti ad essi collegati

## Ereditarieta'

Basare la definizione e implementazione di una classe su quelle di altre classi.

Per l'ereditarieta' multipla si puo' costruire un grafo direzionato (che deve essere per forza aciclico altrimenti tautologia)

Tutte le cose che posso fare con il supertipo lo posso fare anche con la classe sotto. Posso sempre usare un Studente dove mi aspetto una Persona (ma non viceversa).

## Polimorfismo

Posso creare piu' implementazioni per uno stesso metodo.
Si puo' fare con l'`overloading`, permette di creare piu' metodi con lo stesso nome ma con parametri diversi (signature)
Si puo' fare con l'`ovveriding`: permette di riscrivere l'implementazione di metodi della classe padre (nell'ereditarieta'). Puoi specializzare una stessa operazione.

> Una classe astratta non e' istanziabile (manca qualcosa)

