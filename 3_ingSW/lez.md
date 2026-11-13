# 10/11/2026

## Misurazione

Si confronta il software prodotto con le 

## Stima costi

* Se hai gia' fatto un software riusabile e riesci a sfruttarlo per crearne uno nuovo tagli i costi...
* Stabilita' dei requisiti (se non me li cambiano ogni 30 minuti magari si programma prima)

## Dimensioni del software

* Lines Of Code (LOC)

M = mesi uomo tot (impiegati per programmare).

Produttivita': P = LOC/M
Qualita': Q = 

FUNCTION POINTS

### Il metodo Function Points

Restituisce un parametro adimensionale

Misura la dimensione di un software in termini delle funzionalita' offerte.

Valuta quanto e' complesso un software che devi utilizzare (tra due software con


Come si valuta?
Devi contare i punti funzione di un software.
Ci sono 5 categorie di punti funzione, si dividono in:
* funzioni di tipo dati
    * file interni logici
    * file esterni di interfaccia
* funzioni di tipo transazione
    * input esterno
    * output esterno
    * interrogazioni esterne

Per ogni categoria puoi assegnare un punteggio di complessita'.
Sommi tutti i punteggi che hai dato.

#### Tipi di Conteggio

La swHouse mi da una specifica di un software che devo realizzare, conto i FP che devo realizzare (piu' eventuali punti che derivano dal fatto che sono partito da un software vecchio (?))

Mi dicono di aggiungere funzionalita' (manutenzione evolutiva) (puoi anche eliminare funzionalita' o aggiungerne altre), conto i FP.

Ho un applicazione gia' installata, conto i FP iniziali e vado a vedere quelli aggiunti dalla manutenzione evolutiva?

#### Ambito di conteggio

Cosa sto misurando: tutto il software o una sua parte?

#### Funzioni di tipo dati

* File Interno Logico: Ho un gruppo di file che contengono una funzionalita' e sono creati, mantenuti dalla mia applicazione
    Ad esempio pezzi del database (info su clienti, utenti, prodotti, ...), dati di log, help, dati sulla sicurezza (password, accessi, ...)

* File esterno di interfaccia: La mia applicazione li usa ma non li gestisce
    Ad esempio 

#### Funzioni di tipo transazioni

* Input esterno: ad esempio un form (piu' grande e' il form piu' grande e' la complessita'), l'utente mi invia dei dati
* Output esterno: Ad esempio una stampa a schermo, solo se il nostro processo fa delle elaborazioni per calcolare dati derivati
* Interrogazione Esterna: E' come l'output esterno ma non si fa nessuna elaborazione, sputi fuori dei dati che hai gia' pronti.

#### Fattore di aggiustamento

Serve per raffinare la stima per tenere conto di funzionalita' generai del sistema non sufficientemente rappresentate.

CI sono 14 caratteristiche su cui devi dare un numero da 0 a 5 per importanza per il tuo software.
Sommi tutto e poi ho il mio fattore di aggiustamento che poi moltiplico ai miei Function Points (ancora non pesati).


BTW questo metodo e' completamente empirico.

Ora mini-quiz dagli esercizi su sta roba (foto sul telefono).

### Numero Ciclomatico

Da una misura alla complessita' di una procedura (non si usa mai su larga scala).

Ignora completamente i dati (non cambia niente se ho 2 tabelle o 200), misura solo la complessita' del flusso di controllo (quante biforcazioni ci sono)

Nasce dalla teoria dei grafi (il numero ciclomatico si puo' dare ad un grafo). Il grafo deve essere fortemente connesso (da un qualunque nodo puoi arrivare a qualunque altro (no isole).

Il `numero ciclomatico` e' il numero minimo di archi che devo togliere per trasformare un grafo in un albero.

Albero: grafo aciclico in cui scegli una radice e allontani tutti gli altri nodi

Incredibilmente esiste una formula per calcolare il numero ciclomatico di un grafo fortemente connesso.

Ogni nodo e' una istruzione. Ogni istruzione porta in fondo (albero). Aggiungi un arco che dall'ultimo nodo in fondo ti riporta su in cima.
Il numero ciclomatico cosi' calcolato ti da un idea sulla complessita'.

* Formula di Mills: ti permette di calcolare il numero ciclomatico senza disegnare il grafo.

[La complessita' ciclomatica di un modulo non dovrebbe superare il valore 10!]
E' piu' facile da mantenere, fai meno errori...

Ancora un mini-quiz.

### Constructive Cost Model

Stima della dimensione del software: calcolata come
numero di linee di codice scritte (KDSI), può essere fatta
sulla base dell’esperienza del manager oppure utilizzando
una tecnica analitica basata, ad esempio, sul metodo FP:
FP    CLang        NumLinee
1000  20 (Cobol)   20000
1000  32 (Pascal)  32000
1000  40 (C++)     40000
1000  88 (Assembler) 88000

Il numero di linee si puo' stimare dai FP e il linguaggio in cui e' implementato

Poi, dalle linee di codice, si stimano i costi in mesi persona (tempo di lavoro totale).
Devi anche pesare questa stima (?).

Siamo arrivati a p25.

# 13/11/2026

L'ultima volta abbiamo visto la teoria su come misurare un software...

## Modelli di produzione del software

La maggior parte di quelli che vediamo oggi sono detti `prescrittivi` perche' descrivono come fare ogni parte.

Hanno tutti le stesse 5 macro-fasi: Comunicazione, Pianificazione, Modellazione, Costruzione, Deployment.

### Metodo Waterfall (cascata)

Le 5 macro-fasi sono tutte in fila e una volta che ne fai una, passi a quella dopo e a quella prima non ci torni piu' (come una cascata che cade e non puo' risalire).

### Modello Incrementale

Si realizza il software a incrementi:
E' come se partizionassi il tuo software in diversi componenti e per ogni componente fai un metodo waterfall.
E' utile perche' a volte il software e' davvero grande e quindi non e' possibile fare un unico waterfall ma tanti in parallelo

### Modello RAD (Rapid Application Development)

Comunicazione e pianificazione le fai una sola volta per tutto il software.
Le parti di modellazione e Costruzione le parallelizzi in diversi moduli e dividi tra diversi team di ingegneri.
Alla fine il deployment si fa tutto insieme.

E' utile solo se il lavoro per i team non va oltre ai 3 mesi (?).

> [!NOTE]
> [Incrementale vs Iterativo]
> Nell'incremento si aggiunge un nuovo pezzo di software che aggiunge una nuova funzionalita'.
> Nell'iterativo tutte le funzioni sono gia' presenti ma con ogni aggiornamento si migliorano.

### Modelli Evolutivi

Partono dal presupposto che all'inizio gli utenti non sanno bene cosa vogliono, non si sa bene che requisiti deve avere il software.
Questi modelli sono basati su un approccio iterativo.
In questo modo non devi dare subito all'inizio il prodotto finale che non sai neanche cosa vogliono.
Dai un `prototipo`: priva versione un po' per test per capire se sei sulla strada giusta.

> [!NOTE]
> Prototipazione:
> Versione approssimata, parziale (funzionante), dell'applicazione.
> Permette di mostrare qualcosa al cliente per capire se gli piace...
> Riesco a capire per tempo se manca qualcosa, e' sbagliato qualcosa...
> Se il prototipo e' approvato allora si puo' procedere.
>
> Ci sono due modi per fare prototipazione:
> * Prototipazione Evolutiva: il prototipo evolutivamente si trasforma nell'applicazione finale (si presuppone che tu abbia una buona idea dei requisiti).
>   Si rischia di fare un software progettato male (le basi non sono solide), e che quindi avra' vita corta...
>   Questi rischi si possono limitare facendo [refactoring].
> * Prototipazione usa e getta: Si fa perche' non hai capito i requisiti che sono coinvolti in questo prototipo.
>   Lo fai gia' tenendo a mente che probabilmente dovrai fare un'applicazione molto diversa.
>   Riesci a capire una migliore specifica del sistema e poi magari qualche componente rimane riusabile.
>
> La prototipazione e' considerata necessaria soprattuto nella realizzazione dell'interfacce utente.
> Per definire il cosi' detto look & feel come vuole l'utente.

### Modello a Spirale

Si pone come obbiettivo di limitare i rischi nello sviluppo del software.
Ad esempio l'interfaccia potrebbe venire brutta.
Magari ho scelto un linguaggio troppo lento e avevo delle richieste di velocit'a da rispettare.
A ogni giro della spirale si cerca di capire come mitigare i rischi, per il resto invece e' un normale iterativo/incrementale.

### Modello MDA

Model driven Development.
Sfrutta delle tecniche per tradurre modelli in altri... ?

Ci sono i CIM (Computational Indipendent Model) i PIM (Platform Indipendent model) e i PSM (platform specific model).
Astratto -> Meno Astratto -> Platform specific.
Il trucco e' che queste tecniche possono essere automatizzate.
E' lo stesso discorso della progettazione di database: CIM = Progettazione ER (Concettuale); PIM = Schema Logico; PSM = Fisico.
Infatti il diagramma ER puoi tradurlo direttamente in uno schema Logico, il logico in fisico.


> [!NOTE]
> Ora passiamo ai modelli Agili (basta prescrittivi).
> I prescrittivi sono troppo rigidi, non tengono conto delle problematiche che si verificano nella realta'.
> Sono intrinsicamente iterativi e incrementali.
> Manifesto Agile:
> * Il cliente e' al primo posto: consegniamo il prima possibile il software all'utente -> progettazione incrementale;
> * Si impiegano modelli informali per scrivere il codice: POCO UML, POCA INGEGNERIA DEL SOFTWARE;
> * Semplicita' di sviluppo, piccole\semplici funzionalita';
> * Comunicazione continua con l'utente (potrebbe non essere possibile).

### Extreme Programming (E' Agile)

Approccio Object Oriented.
4 passi:
* Painificazione:
    * Definisco le funzionalita' che deve avere il software (chiamate `user story`).
    * Ad ogni user story viene dato un valore di priorita'
    * Si cerca di capire quante settimane ci vogliono per ogni user story
    * Se una usery story richiede piu' di 3 settimane la spezzo
* Design:
    * Semplicita'
    * No funzionalita' aggiuntive
    * Se c'e' un problema di design si crea immediatamente una `spike solution` che e' un microprototipo per capire se puo' andare
    * Si incoraggia il `refactoring`
* Programmazione:
    * `Pair programming`: metto due programmatori alla volta cosi' 4 occhi trovano meglio problemi e cosi' li evito.
* Testing:
    * Gia' all'inizio della programmazione si definiscono dei test per ogni singolo componente. Devono essere automatici (tipo JUnit).
    * `Test di regressione`: quando aggiungi una nuova funzionalita' (che puo' interagire con quelle vecchie) devi ritestare anche le vecchie.

Se mi accorgo che nella prima iterazione avevo troppa roba, nella prossima iterazione aggiusto (in modo da consegnare sempre il codice nella stessa finestra di tempo).

### Unified Process

Forse e' un po' meno usato.
Dovrebbe essere il processo utilizzato dopo UML (e' stato progettato dagli stessi che hanno fatto UML).
E' un po' complesso, vediamo solo l'intuizione.
UP = processo teorico
RUP = programma che gestisce UP

NOn ne posso piu'
Ogni flusso di lavoro ha 4 fasi.
Le fasi sono sequenziali, I flusis no.
In ogniw

---

## Verifica del software

L'obbiettivo e' controllare se il software che stiamo realizzando aderisce alle specifiche.
Esistono due famiglie di tecniche di verifica: Dinamica (verificano il software facendolo funzionare, mettendolo in esecuzione) e statica (verifico il software andando a guardare il codice).

### Testing

Non potro' mai testare ogni singolo caso del mio software. Posso testare solo un numero finito di casi prova.
* Testing in the small: dato un pezzetto di codice particolarmente critico devo accertarmi che dia sempre l'output desiderato per ogni input;
    Devo avere un metodo white box su cui fare questo test: non e' solo una scatola nera, so anche il codice della procedura.
    Ci sono diversi livelli di testing in the small:
    * [Statement test]: Almeno devo cercare di mettere in esecuzione ogni singola riga di codice almeno una volta.
        Cio' non significa che trovo gli errori ma almeno devo vedere tutto in esecuzione, mi sembra il minimo.
    * [Branch test]: Non basta solo mettere in esecuzione ogni istruzione almeno una volta. Devo coprire anche tutte le guardie almeno una volta.
        Se c'e' un if then (anche senza else!) devi farlo fallire anche! (invece nello statemnt test ti basta entrare nel then, tanto esegui tutto)
        Non basta passare tra tutti i nodi, devi anche passare per tutti gli archi.
    * [Criterio di copertura delle decisioni e delle condizioni]: nn h cpt.
* Testing in the large: definisco degli scenari globali e vedo se funzionanan
