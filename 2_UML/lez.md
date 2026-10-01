# UML 22/09/2026

UNIFIED MODELING LANGUAGE (ha riunificato tutti i modelli che c'erano prima con la collab tra Booch, Jacobson, Rumbaugh che erano tra i creatori di modelli che vedi a fine del pdf 2).
E' uno standard aperto (a modifiche?).
E' stato standardizzato nel '97.

Esistono dei potenti strumenti CASE che possono creare codice a partire da UML e viceversa.

> [!WARNING]
> UML e' un linguaggio, non un METODO! (come quelli a fine pdf 2)
> Puoi usare un metodo scrivendo con UML.

E' descritto con un metamodello? cioe' UML e' autodefinito con del codice UML.

Uml copre tanti fasi del ciclo di vita del codice.

Un diagramma e' una vista di un modello. Il modello di una nave e' una navi piu' piccola un po' semplificata.
I diagrammi ci fanno vedere un modello da un particolare punto di vista.

![Parte di Metamodello di UML](./metamodello.png)


Forse per questa parte conviene di piu' stare sul pdf (tante immagini).
Vabbe' per ora ci provo:

## Entita'

![Entita](./entita.png)

Non useremo mai la Collaborazione (godo).

Un componente e' un modulo (tipo una libreria)
Un nodo e' un dispositivo hardware (server, pc, stampante, ...). Un componente puo' essere messo dentro un nodo per dire che il nodo supporta quel software (del componente).

Comunque le vedremo una ad una...

Dentro ad un package posso mettere tanti elementi del modello che sono correlati (classi che svolgono operazioni simili).
Annotazioni molto utili (anche per rappresentare un vincolo non facilmente esprimibile altrimenti in un linguaggio naturale).

## Relazioni

Legano tra loro le entita'

![Relazioni](./relazioni.png)

Dipendenza - un entita' A dipende da una B se una modifica in B puo' implicare una modifica in A.
Aggregazione - Part of (debole);
Composizione - Part of (forte);
Realizzazione (NON LA USIAMO NEGLI ESERCIZI)
Contenimento - si usa solo nei diagrammi di package per dire che un package ne contiene degli altri.

## Diagrammi

Sono viste sul modello UML.

### Statici:
* Diagramma delle classi `-` (quelli contrassegnati con questo simbolo possono uscire all'esame)
* Diagramma degli oggetti (compare meno raramente dei diagrammi delle classi)
* Diagramma dei package
* Diagramma dei componenti
* Diagramma di deployment
* Diagramma delle strutture composite

Dinamici:
* Diagramma dei casi d’uso `-`
* Diagramma degli stati `-`
* Diagramma di attività `-`
* Diagramma di interazione
    * Diagramma di sequenza `-`
    * Diagramma di comunicazione
    * Diagramma di sintesi dell’interazione
    * Diagramma dei tempi

# 29/09/2026

# Statici

## Diagramma delle classi

Attraverso questo diagramma si modellano le costituenti fondamentali del nostro sistema.
Classi diagramma di tipo statico.
E' simile all'entity relationship.

### Diagramma degli oggetti

E' una istanza del diagramma delle classi, in effetti non si usa molto ma e' utile per i progettisti per inserire le tuple nel sistema (e' un esempio di come fare).

## Diagramma dei package

Insiemi di classi che collaborano per svolgere una funzionalita' comune

### Diagramma dei componenti

Descrive l'architettura software del sistema

### Diagramma di deployment (schieramento)

Descrive l'architettura hardware del sistema

# Dinamici

## Diagramma dei casi d'uso

Non e' proprio dinamico, elenca le funzionalita' che il sistema puo' svolgere.
Viene creato mettendosi nei panni dell'utente (non di chi progetta il software).

E' il primo diagramma che si disegna quando si inizia la fase di analisi.

## Diagramma degli stati

Facciamo vedere in che modo gli oggetti di una classe reagiscono ad eventi esterni cambiando stato.

## Diagramma di attivita'

Simile al diagramma degli stati. Pero' puo' incorporare anche il diagramma funzionale.
E' perfetto per documentare un workflow.

## Diagrammi di interazione

Sono principalmente funzionali ma c'e' anche una componente dinamica.
Ci fa vedere come gli oggetti interagiscono tra loro scambiandosi messaggi tra loro.
Se A manda un messaggio a B vuol dire che A chiama un metodo di B.

### Diagramma di sequenza

L'unico diagramma di interazione che vedremo.
Enfatizza l'ordine temporale con cui gli oggetti si mandano messaggi.

### Diagramma di comunicazione, ...

Ce ne sono altri di diagrammi di interazione ma non li vedremo.

# Specifiche (p11)

# Ornamenti

Aggiunte che si possono aggiungere alle specifiche (le metteremo senza neanche accorgercene)

# Distinzioni comuni

## Classificatore \ Istanza

(Istanza = oggetto, una specifica cosa; Classificatore = classe, quella cosa in generale)
In uml le Istanze dei classificatori hanno lo stesso nome ma sono sottolineati.

## Interfaccia \ Implementazione

Per un interfaccia devi scrivere `<<interface>>` (e' uno stereotipo).
Ovviamente un interfaccia non ha struttura, non e' istanziabile, e' astratta.
I metodi vanno scritti in corsivo.
Le interfacce possono essere REALIZZATE (freccia tratteggiata vuota)

# MEccanismi di estendibiltia'

## Stereotipo

E' il principale meccanismo di estendibilita' di UML (per estendere le sue funzioni).
Dici praticamente che quell'elemento non e' proprio quello normale del linguaggio ma e' una cosa un po' piu' particolare.
E' una variazione di un elemento di modellazione esistente.
Ce ne sono di predefiniti (tipo <\<interface>>).
Il programmatore puo' introdurne di nuovi.

## Proprieta'

Associa ad un elemento del modello un valore, una stringa.

## Vincoli

Definisce una regola a un elemento del modello
Ad esempio nelle gerarchie ER potrei avere {disjoint, complete}

## Profilo

Un progettista puo' creare un set di stereotipi, proprieta' e vincoli per personalizzare l'UML a piacere.
Esistono dei profili predefiniti standard.

# Architetture

Sono viste diverse che si possono rappresentare sul nostro modello (non molto importante).
Noi lavoreremo sempre a vista dei casi d'uso e vista logica.

FORZA INIZIAMO!

# DIAGRAMMA DEI CASI D'USO

Diagramma funzionale che mostra come gli utenti usano il sistema attraverso casi d'uso (funzionalita').
Gli utenti possono essere altre persone, organizzazioni o anche altri sistemi software.
Comprensibile a chiunque. Infatti serve anche a comunicare con il cliente (non tecnico).
Questo diagramma continua ad essere importante per tutto il ciclo di vita del software. Ad esempio dopo l'implementazione c'e' la fase di test (collaudo) che viene fatta guardando i casi d'uso e si verifica che funzionino. Puo' essere anche usato oer guidare il `rilascio incrementale` del software (a volte il software viene rilasciato a pezzi, "il prossimo mese ti rilascio questi nuovi casi d'uso")

## Attore vs Casi d'uso

Ad esempio per il sistema di Alma esami noi studenti siamo `Attori`.
L'attore scambia informazioni con il sistema, noi ci scriviamo agli appelli e possiamo consultare gli appelli.
L'attore ATTIVA un caso d'uso (iscrizione ad un esame).
L'attore e' sempre una classe, non un oggetto (no istanze).

Il caso d'uso e' sempre attivato da un attore.
Il caso d'uso e' una funzionalita' come percepita da un attore.

![Casi d'uso di una Banca](./casidusobanca.png)

Gli omini sono gli autori.
Le linee nere sono dal punto di vista sintattico delle ASSOCIAZIONI. In particolare sono delle ASSOCIAZIONI DI COMUNICAZIONE, l'attore comunica con il caso d'uso.

I casi d'uso sono i cerchi.
L'attore dal punto di vista sintattico e' un

## Relazioni nei diagrammi di casi d'uso

In questi diagrammi si possono anche disegnare relazioni aggiuntive.

* Puo' esserci generalizzazione tra attori (come nelle ER (gerarchie)).
* Le comunicazioni unidirezionali (da non abusare, normalmente sono bidirezionali) si fanno con una freccia ad esempio stampa rapporto
* Generalizzazione tra casi d'uso: Alcune operazioni sono anche altre operazioni (is a).

![Relazioni Nei diagrammi dei casi d'uso](./relazionicasiduso.png)

Le dipendenze vanno quasi sempre stereotipate, cosi' spieghi come viene fatta
Ad esempio Prelievo bancomat si puo' fare solo se fai anche la verifica di identita'. Quando sto prelevando mi viene anche verificata l'identita'. La `<<include>>` serve proprio a questo. Devi immaginarti che nella procedura prelievoBancomat() c'e' anche una chiamata a verificaIdentita().
Per le chiamate opzionali si usa la relazione di dipendenza con stereotipo `<<extend>>`. Significa che il caso d'uso principale non sempre chiama quello che estende. Anche in questo caso si puo' vedere come una chiamata di procedura ma che e' opzionale.
La liberatoria per libri rari e' un'estensione per la richiesta prestito (va letta al contrario).


## Come disegnarli

* Prima identifico i confini del sistema (magari non comprende tutto il dominio)

* Poi si inizia disegnando gli attori.

* Per ogni attore ci si chiede come interagisce col sistema e si disegnano i loro casi d'uso.

Poi ci sarebbero anche queste fasi:

* Noi non lo faremo ma nel mondo reale insieme al diagramma dei casi d'uso bisogna fare anche gli `scenari` che non sono altro che istanze dei casi d'uso. Bisogna documentare gli scenari di successo (vado in banca e prelievo) e di insuccesso (vado in banca, ho dimenticato il documento e non posso prelevare) che fanno fallire il caso d'uso. Questa parte non e' modellata da UML ma esisterebbero i diagrammi di attivita' o sequenza ma sticazzi.

* Per ogni caso d'uso poi dovrei fare una mini tabella con descrizioni, attori che coinvogle (primari (attivano il caso d'uso) e secondari), precondizioni (per registrarmi ad un appello devo avere eseguito l'accesso su almaesami), postcondizioni (dopo l'iscrizione sono effettivamente iscritto all'appello, appaio nella lista), sequenza degli eventi

### Realizzazione dei casi d'uso

Come prima con la interfaccia 

Ora stiamo facendo un paio di esercizi sui casi d'uso.
Esercizio negozio articoli per la casa. Evidenziamo gli aspetti statici, dinamici o funzionali nel testo.

Ecco gli esercizi:

![Esercizio 1](./es1.jpg)

![Esercizio 2](./es2.jpg)


