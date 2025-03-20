#Uni/Insegnamenti/Secondo_Anno/RC 
marco.tocco@unica.it
Iniziare le mail con `[RC]`
# Hardware di rete
Le reti possono essere divise e categorizzate per diverse proprietà
## Caratterizzazione per tecnologia trasmissiva
Caratterizziamo le reti basandoci sulle caratteristiche dei collegamenti e sulle modalità con cui l'informazione viene trasmessa
- Broadcast: il messaggio da inviare passa in maniera "libera" sul canale trasmissivo e raggiunta da tutti gli host sulla rete
- Punto a punto: il messaggio passa da un canale trasmissivo diretto tra i due host che devono comunicare
### Collegamenti punto a punto
Il nodo di origine specifica il destinatario
- I dati possono visitare diversi nodi intermedi
- Possono esistere percorsi multipli per connettere i due nodi interessati, quindi è necessario implementare algoritmi per riconoscere il percorso migliore
### Broadcast
Abbaimo un canale di comunicazione condiviso su cui sono trasmessi/ricevuti tutti i dati
Alla ricezione ogni nodo controlla l'indirizzo del destinatario e se si tratta del proprio lo elabora, altrimenti lo scarta
Esistono tra tipologie
- Broadcasting: a tutti
- Multicasting: a una parte degli host sul bus
- Unicasting: il messaggio è indirizzato a solo un host
## Caratterizzazione per topologia
Basato sulla forma geometrica che descrivono, ovvero come sono implementati i collegamenti tra i vari host:
- Fully connected (Connessione diretta tra ogni host), non più utilizzata
- Line difficilmente utilizzata a meno di casi specifici

### Topologia a Bus
Abbiamo un canale unico portante, che arriva in tutta la rete, a cui è connesso ogni host. 
- Semplice da realizzare e poco costosa
- Risulta sensibile ai danni e risulta difficile trovare il punto di guasto
- È necessario utilizzare una comunicazione broadcast
- È quindi ora meno utilizzata
### Topologia ad anello - Ring
Ogni dispositivo della rete è collegato ad altri due, andando a formare un circuito chiuso in cui i dati sono mandati in una unica direzione
- Ampiezza di banda e tempi di attesa deterministici perchè la distanza tra ogni nodo della rete non cambia nel tempo.
- Non necessita di amplificatori di segnale
- Ormai dismessa per la bassa economicità e in alcuni casi poco affidabile
### Topologia a stella
Abbiamo un hub centrale a cui tutti i dispositivi si connettono. L'hub ha il compito di costituire i canali di comunicazione con i diversi host. Topologia tipica della tecnologia Ethernet moderna
- Diffusa per l'economicità dei componenti
- Facilmente scalabile
- Utilizzo di cavi maggiore
- Nonostante sia più resiliente nel caso di rottura di un solo host, abbiamo un blocco completo nel caso di guasto dell'hub (che costa comunque di meno rispetto al rame)
## Per scala di interconnessione
Si basa sul livello di estensione geografica dell'area nella quale i nodi sono interconnessi
### PAN
Reti personali
Hanno un estension di irca 1 m
Tipicamente costituite da segnali radio
Usano spesso il paradigma master-slave
Esempi: connessione di mouse e cuffie a pc e cellulari

### LAN
Sono le reti che si estendono dall''interno di un edifico, fino a un campus con ampiezza di qualche chilometro
Sono caratterizzate da
- Dimensione contenuta
- Topologia bus/stella/anello
La creazione di una rete locale fa parte degli standard IEEE 802
- 802.3 che descrive le prime reti Ethernet (CSMA/CD)
- 802.11 che descrive le reti wireless
### IEEE 802.3 CSMA/CD
- Derivato dalla tecnologia Ethernet nel 1985
- CS: ogni nodo ascolta continuamente il mezzo trasmissivo
- MA: il mezzo trasmissivo è condiviso da tutti i nodi
- CD: collision detection: i nodi sono in grado di rilevare collisioni dovute alla trasmissione simultanea e reagire di conseguenza
Era utilizzato nelle reti dove si aveva un unico hub e un unico canale trasmissivo (bus)
### IEEE 802.4 Token Bus
I nodi sono collegati con topologia bus. Per risolvere il problema delle collisioni, utilizzava però un sistema di token, creando una tipologia virtuale ad anello, attraverso cui viaggiava il token e solo chi aveva il token poteva condividere in broadcast il proprio messaggio. Passava poi il token all'host successivo
### IEEE 802.5 Token Ring
Evoluzione di 802.4 con funzionamento relativo al token equivalente, ma con topologia ad anello. Il messaggio salta tra i vari host, fino a tornare all'host mittente. Quando il mittente, avrà la certezza che il messaggio sia arrivato a tutti gli host della rete, cederà il token (un po' come il gioco del telefono)
### IEEE 802.11
La famiglia di Questi standard definiscono le reti LAN di tipo wireless
Le reti senza fili hanno diversi problemi intrinseci, come interferenze con alti dispositivi, la portata di ogni stazione, o la necessità di limitare l'estensione della rete (si utilizzano schemi crittografici)

### MAN
Sono reti che coprono tipicamente una intera città, con un'estensione di una decina di km, secondo gli standard IEEE 802.6, 802.16, 802.17

### WAN
Sono reti di area molto ampia, coprendo spesso anche stati o interi continenti
Integrano al loro interno sottoreti, formate a sua volta da altri elementi di commutazione (come router e switch), mentre gli host sono disposti su un'altra sottorete
### Internetworks
Sono reti che interconnettono reti di tipo differente, o reti differenti della stessa tecnologia

# Software di rete
## Gerarchie di protocolli
Ogni rete è vista come una pila di stati o livelli
- Si riduce così la complessità
- Si favorisce un approccio modulare
- Ogni strato fornisce servizi allo strato superiore, nascondendogli i dettagli implementativi
In base alla tipologia di rete, variano 
- i numeri di strati
- Il nome degli strati
- I compiti che ogni strato svolge

Ogni livello ha delle funzioni precise e interagisce direttamente con il livello corrispondente dell'host del destinatario, utilizzando protocolli di pari livello.
Un singolo host fa scendere/salire i dati nella pila attraverso le interfacce
### Entità paritarie
Si dicono Entità paritarie o peer, le entità che formano strati di pari livello su differenti host.
La comunicazione tra peer di livello `n`, comunicano virtualmente mediante il protocollo che è stato definito per il livello `n`
### Protocollo
Un protocollo è l'insieme di regole sul formato e il significato delle informazioni inviate tra peer di un livello n
### Interfacce
Le interfacce regolano lo scambio di informazioni tra due livelli immediatamente successivi dello stesso host.
Sono essenziali perchè i peer non comunicano in modo diretto, forniscono funzioni per i livelli superiore e inferiore per supportare effettivamente il trasferimento di dati

### Architettura di rete
Si definisce Architettura di rete, l'insieme di livelli e protocolli che vengono utilizzati 
Non fanno parte dell'architettura di rete:
- Dettagli implementativi di ogni strato
- Specifiche delle interfacce: tra host diversi le interfacce possono essere implementate diversamente (win, macos, linux), ma questo non inficia la comunicazione

Le reti sono progettate in maniera modulare

## Gestione della comunicazione

Consideriamo una pila di esempio di 5 livelli
1. Il messaggio `M` viene generato al livello più alto
2. Il messaggio è trasferito al livello 4, tramite l'interfaccia
3. Il livello 4 aggiungerà un header in testa al messaggio `H4|M`
4. Il messggio con l'header è trasferito al lvl 3
5. Lo stato 3 spezza il messaggio in unità più piccole M1 e M2 e ne aggiunge il suo headere
6. Viene passato al lvl 2
7. Aggiunge un header a entrambi i pezzi di messaggio
8. È passato al livello 1
9. Il livello 1 trasformerà il messaggio in uno stream di bit per mandarlo all'altro host
10. Il ricevente andrà ad analizzare e rimuovere gli header, ricomporre ciascun pacchetto fino a quando non si riotterrà il messaggio originale

### Sottorete di comunicazione
Molto spesso il messaggio non passerà direttamente da host a host, ma passaerà attraverso degli altri host, che lavorano ai livelli più bassi per raggiungere con successo il destinatario richiesto

### Considerazioni
È importante capire che la comunicazione tra pari è virtuale e l'unica comunicazione effettiva avviene tra strati adiacenti attraverso le interfacce

## Progettazione dei livelli di una rete
Qualora volessimo progettare una nuova rete, è necessario tenere conto di alcune proprietà necessarie per la nostra rete.
- Ogni stato deve occuparsi dfelle proprie funzionalità, senza interferire con gli altri livelli
- Per alcuni elementi indispensabili (come la correzione delgli errori) è possibile prevedere un certo livello di ridondanza
- Gli strati superiori devono essere sicuri che ciò che ricevono dagli strati inferiori sia corretto

### Indirizzamento
È uno degli strumenti essenziali per una rete.
Ogni livello deve identificare da dove un pacchetto gli è arrivato e dove deve andare
Sia tra host, che da quale processo è arrivato.
Questo sistema è implementato tramite i Service Access Point (SAP)
Ogni livello utilizza i SAP, che assumono però un nome diverso
- Lvl 2 indirizzo MAC (rete giusta)
- Lvl 3 indirizzpo IP (macchina giusta)
- Lvl 4 porte (applicazione giusta)
### Regole di trasferimento
È un insieme di regole che determinano in quale senso possono viaggiare i dati
- Simplex: monodirezionale (radio FM)
- Half duplex: una firezione per volta (walkie-talkie)
- Full duplex: entrambe le direzioni contemporaneamente

Spesso definiscono a quanti canali logici esistono sulla trasmissione

### Controllo degli errori
Esistono meccanismi che consentono di rilevare e/o correggere errori avvenuti durante la trasmissione dati, perchè i ciricuito fisici non sono perfetti, ed è quindi probabile che avvenga il flip di un bit

È possibile rilevare l'errore solamente e richiederne la ritrasmissione (bit di parità), o rilevarlo e correggerlo (distanza di Hamming)

Sorgente e destinazione dovranno accordarsi sul metodo di gestione da usare e sul metodo per informarsi su quali messaggi siano stati trasmessi correttamente

### Controllo della sequenza
È un meccanismo che consente ad un destinatario di verificare e riassemblare i dati nello stesso ordine con cui sono stati inviati dal sorgente.
Esistono due tipologie di comunicazioni:
- Connection oriented (ordine garantiti)
- Connectionless (ordine non grantito)

È necessario etichettare le informazioni con numeri di sequenza per ristabilire il loro ordine e ripristinare le informazioni, una volta arrivate a destinazinoe

### Controllo di flusso
Vogliamo impedire che una sorgente invii dati troppo velocemente e sovraccarichi o saturi una connessione lenta

È possobile gestitre il controllo del flusso
- Con...
- --...
- ...
È tratttato ai livelli 2 e 4

### Multiplexing e demultiplexing
Sono meccanismi che permettono di separare i dati del sorgene e inviarli parallelamente per aumentare la velocità di trasferimento
Le parti più piccole sono riassemblate a destinazione
### Routing
È il meccanismo che consente di indirizzare i dati lungo il (possibilmente miglior) percorso tra sorgente e destinazione. O anche evitare che il messaggio attraversi determinati nodi della rete.
Un algoritmo di routing si occupa di calcolare questo percorso, in base alle diverse esigenze.
Sono gestiti dai router, dispositivi ad-hoc che implementano solo i primi tre livelli di una rete

## Comunicazione tra livelli adiacenti
### Relazione tra interfacce e servizi
Un generico livello `n`
- Riicheide i servizi forniti dal lvello sottostante (service provider)
- Implementa il proprio protocollo
- Offre i propri servizi al livello superiore (service user)

I servizi sono richiesti tramite interfacce, definibile come
- Operazioni primitive e servizi richiesti da lbl n a n-1
- Operazioni primitive e servizi offerti da un lvl n a n+1

Una buoina progettazione delle interfacce consente di
- Minimizzare le informazioni da. Scambiare tra libelli adiacenti
- Aggiornarne l'implementazione senza influenzare altri livelli

### Service Access Point
Sono i punti di accesso che un entità di livello superiore può accedere ai servizi del livello sosttostante
Un sap è definito univocamente da un indirizzo
### Passaggio delle informazioni
Nel passggio delle informazioni tra livelli, i dati subuscono trasformazioni per renderle più adatte all'elaborazione nel livello inferiore

Nel lovello n, il dato è preparato `n-PDU`
Nel livello n-1, `n-PDU` diventa `n-1-SDU` e gli viene aggiunto `n-1-PCI`  e compongono `n-1-PDU`
Prima di passarlo al SAP, sono aggiunte le ICI, che contiene informazioni interpretabili dal SAP

### Nomenclatura di PDU e PCI
1. Bit
2. Frame o Trama
3. Pacchetto
4. Transport PDU o Segmento
5. Session PDU
6. Presentation PDU
7. Application PDU