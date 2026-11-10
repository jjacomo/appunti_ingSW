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
