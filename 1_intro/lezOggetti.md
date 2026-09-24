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

Riusabilita' e estendibilita' (facile da estendere, ottengo mantenibilita')

Il polimorfismo funziona grazie al `late binding` (istanziamento dinamico)
Esempio lista di figure geometriche: il supertipo e' figura geometrica, si specializzano in figure concrete (quadrato, cerchio, ...).
Lancio su tutta la lista il metodo rotate(). Il compilatore non sa che metodo specializzato chiamare (se quello del quadrato, del cerchio o altri. Quindi in questo caso si effettua il late binding. A runtime (non compile time) guarda che oggetto e' quello della figura geometrica e lancia il suo metodo rotate() (addirittura quello della classe padre era vuoto (era una classe astratta)).

## Delegazione

Un oggetto delega ad un altro delle operazioni (perche' e' gia' li' e le fa meglio).
Ad esempio potrei avere una classe String con tante belle utilities per le stringhe.
Se poi creo una classe Persona che usa diverse stringhe al suo interno (tipo nome, congome) faccio i campi di tipo Stringa, non (char*).

La delegazione si ha anche quando collego uno studente ai suoi esami.

Quindi si verifica sia quando dentro una classe ci metto dentro un altra che mi serve per delegare delle operazioni (tipo Persona e Stringa) oppure si verifica anche quando collego un oggetto ad un altro (tipo dentro uno Studente metto un puntatore a Corso).

* L'associazione (riga 72 di questo file) e' un meccanismo di astrazione che nel paradigma ad oggetti e' implementato dalla delegazione.


## Nascita del paradigma ad oggetti

Nasce negli anni 60 coi primi linguaggi talebani della programmazione ad oggetti.
Poi C++ negli anni 80 che da il via poi a java e python che oggi sono popolarissimi.

L’obiettivo principale dell’approccio orientato agli oggetti (OO, object-oriented) è migliorare la produttività aumentando l’estendibilità e la riusabilità del software e controllando la complessità e i costi della manutenzione.

Dall'approccio funzionale (che abbiamo detto che conviene poco perche' le funzionalita' cambiano spesso nel tempo).
Si passa dall'approccio ad oggetti.

* ANALISI: va dall’inizio del progetto fino all’analisi delle specifiche utente e allo studio di fattibilità (cosa il sistema deve fare)
* DESIGN: progettazione logica e fisica del sistema (come lo deve fare)
* IMPLEMENTAZIONE: scrittura del codice, test di verifica, validazione, manutenzione
    * I confini tra le fasi non sono più distinti, infatti il centro di interesse è lo stesso: gli oggetti e le loro interrelazioni
    * Il processo di sviluppo OO è iterativo: si adotta il modello a fontana, in cui lo sviluppo raggiunge un alto livello per poi ritornare a un livello precedente e risalire di nuovo
    * L’ereditarietà permette di aggiungere nuove caratteristiche a un sistema riducendo i costi di manutenzione (estendibilità), e di costruire nuove funzionalità a partire dall’esistente (riusabilità) riscrivendo solo quella parte di codice inadeguato e solo per gli oggetti che ne hanno bisogno

Una classe in pratica e' un modulo quindi stiamo anche applicando il principio di modularizzazione.
Il codice si basa sulla parte statica del dominio quindi in genere il codice ha vita piu' lunga.

Diminuiscono i costi di manutenzione.
Non devo creare ne classi enormi ne classi minuscole. Qual'e' il criterio per decidere? Le classi che creo devono corrispondere ad un elemento del dominio applicativo. (p24 OOAnalisis)

C'erano diversi metodi di programmazione OO che poi hanno dato vita ad UML che ha sostituito tutti gli altri.
Oggi UML e' l'unico linguaggio che su usa oggi.


