#Uni/Insegnamenti/Secondo_Anno/RC 
Cosa pensa una persona normale delle reti di calcolatori?
- Una parte esplicita per l'utente, che intende una serie di macchine connesse tra loro
- Per noi lo possiamo interpretare coma una serie di sistemi che si ramificano: una rete locale è un piccolo strato della rete
- LAN: tutti conoscono tutti, la quantità di host è nota, è sufficiente una comunicazione broadcast. L'insieme implicito è ridotto
- MAN: in una rete metropolitana ho bisogno di connettere tra di loro livelli differenti
- WAN: scaliamo talmente tanto che abbiamo bisogno di indirizzare macro-regioni di macchine

### Reti per aziende
- Condividere risorse: per condividere risorse abbiamo bisogno di conoscerne l'indirizzamento
- Alta affidabilità: si parla di affidabilità perché è necessario garantire che il dato arrivi alla fine: l'affidabilità cresce nel tempo e deve essere garantita attraverso sistemi particolari. Ad esempio nei contratti i connessione domestica è segnata la garanzia di affidabilità del gestore
- Risparmio economico: ogni rete può utilizzare direttrici di proprietà o direttrici di terzi, in affitto
- Modello client-server: un utilizzatore della rete fornisce molti servizi, poi il client accede a questi servizi

### Reti per persone
Da un punto di vista della struttura delle diverse architetture, possiamo dividerle, tra un consumatore semplice, come un client, un sistema più vicino al modello del server, fino a un governo

I dispositivi personali rappresentano un nodo della rete, l'esempio minimo di un nodo della rete è un sensore di vari tipi, come termici, di presenza, etc...

Differenziamo, nell'accesso ai sistemi di comunicazioni

### Hardware delle reti
Introduciamo due concetti, dividendo in hw delle reti e sw delle reti.
Nelle reti, comunichiamo il destinatario, il mittente e i dati inviati. Le dimensioni di una comunicazione sono circa 32 bit 32 bit 1500 kb. 
Il termine "pacchetto" è comunemente utilizzato, ma è proprio solamente del livello rete, a livello inferiore si parla di trame, a livelli superiori si parla di segmenti. A livello fisico abbiamo solo flussi di bit

Nelle reti broadcast il pacchetto dovrà presentare caratteristiche come, il non presentare un destinatario univoco
Nelle reti multicast si crea una particolarità, in quanto non condividiamo con tutti i presenti, in queste reti, identifichiamo i nodi come appartenenti ad alcuni sottoinsiemi (anche svrapposti)
Nelle reti point-to-point abbiamo una macchina sorgente che comunica con una macchina ricevente. Questa categoria è la più costosa e pesante da gestire, perché è necessario definire il percorso per raggiungere la destinazione

Classifichiamo quindi le reti in tre categorie: LAN, MAN, WAN; possiamo anche definire altre categorie accessorie come Wireless Networks, Home Networks, Internetworks (Reti di reti).

Una delle ipotesi di classificazione si può definire sulla distanza che copre una rete

### Reti locali
Le classifichiamo per dimensione (non la densità delle macchine), tecnologia trasmissiva (fibra, wireless, ...), topologia (come sono distribuite le macchine nel territorio), protocolli

### Reti metropolitane
Un esempio di architettura della rete metropolitna è 

### Reti geogradiche
Relazioni tra host e sottoreti di comunicazione (subnet), che si occupa di connettere tra loro reti diverse.
Le sottoreti sono costruite da due tipologie di dispositivi

### Inter-reti
Due reti wide-area, diverse, possono essere collegate tra di loro per mezzo di un gateway che potrà interfacciare e tradurre (generalmente) tutti i livelli di comunicazione delle due reti

## Software delle reti
### Gerarchie dei protocolli
Per gestire questi livelli, permettiamo la comunicazione tra protocolli livello-equivalenti, per ridurre la complessità delle reti, perché ogni livello assolverà ai compiti specifici di ciascun livello.

La struttura per poter far colloquiare i livelli si chiama protocolli, tra livelli adiacenti, la comunicazione avviene con la cosiddetta **interfaccia**, che definisce le primitive di comunicazione tra i livelli.

- Attenzione: mezzo fisico, non implica che sia un cavo vero e proprio

L'insieme dei protocolli prende il nome di **architettura di rete**

Se si richiede di mandare, deve oria esse organizzato in header

La funzionalità molto comoda dei protocolli è che , modificare, anche solo uno dei protoclli, non potrà incidere sui protoclli degli altri livelli

Si dice **astrazione dei processi pari**; l'insieme dei protocolli 

Ad una connessione possono corrispondere più canali logici

Alta velocità del mittente in confronto con la bassa velocità del destinatario

Lunghezza dei messaggi: possiamo frammentare i pacchetti per avere una comunicazione più rapida

### Interfacce e servizi
In un livello particolari si definisce una **entità**: una parte sw e una hw: interfaccia

Abbiamo quindi una fornitura dei servizi, verso un utente dei servizi, al livello superiore. Il punto dove avviene questo scambio si chiama SAP - Service Access Point

### Servizi orientati alla connessione e servizi privi di connessione
Abbiamo due tipologie di servizio:
- I  Servizi orientati alla connessione, indicano che è necessaria una connessione continua tra le macchine
- Nei servizi privi di connessione, indica che non esiste una connessione continua, potendo utilizzare anche diversi percorsi per parti diversi

QoS: quality of service

Servizi datagramma con messaggio di ricevimento: non è necessario l'ack, quando la rete è completamente affidabile+

### 17.03 Primitive di servizi
La volta scorsa abbiamo diviso i nodi di una rete in host e router, ognuno di questi router sono di diversi livelli. Gli host, tra di loro, possono avere un rapporto tra pari (scambiano dati) o client-server (una macchina genera e una macchina riceve servizi).
Questa architettura ha insieme una serie di operazioni (primitive fondamentali della comunicazione) -- esempi colloquio zia Millie

### Servizi e protocolli
Un protocollo non è altro che un programma che si occupa di mettere in comunicazione livelli pari ($n$, con $n$). Non potranno mai comunicare livelli differenti.
Il vantaggio che abbiamo dalla parità di questi livelli è che gli stessi livelli "parlano la stessa lingua" e che facendo una modifica su un modello, questo è modificato su tutte le macchine. Non cambiamo la comunicazione tra altri livelli

Pur colloquiando tra diversi livelli, l'unico collegamento è al livello più basso (mezzo condotto - cavo o non condotto - wireless) e poi faccio il de-envelop

un **protocollo** e’ un insieme di regole che governano il formato e il significato delle informazioni che vengono scambiate tra entità pari di un livello i-esimo

### Modelli di riferimento
- UTILIZZARE SEMPRE I SUOI SCEHMI
La parte riquadrata è la sottorete di comunicazione, ovvero i router che sono tra i due host interessati dalla comunicazione (possono essere molti, non solo due).
Il modello utilizzato non è uno standard *de-facto* (diventa uno standard come TCP/IP), ma uno standard teorico, di riferimento: il modello ISO-OSI.
Il router è un elaboratore specializzato nell'interconnessione tra macchine, non ha quindi bisogno di arrivare al livello applicativo, ma basta arrivare al livello di rete (IP nel TCP/IP).
Nella connessione host-router al livello fisico, abbiamo una specifica di interfaccia (come avviene il collegamento).
Il livello rete, proprio della comunicazione, è l'unico livello dove utilizziamo il termine **pacchetti**

![[Pasted image 20250317164831.png]]

"Qual'è il significato, la definizione e di cosa si occupa il livello di x? "- È necessario darne una definizioine minima

Ogni livello scambia dati propri del livello: dati, indirizzi di sorgente e destinazione e un campo di controllo

### Livello fisico
- Unico Livello con connessione diretta per il trasferimento di bit
- Controllo del voltaggio da attribuire al bit (voltaggi bassissimi, appena abbastanza da non causare dispersione e da essere riconosciuti non come errori) - qualità di invio
- Per quanti microsec trasmettere il bit - quantità di invio
- Se è possibile viaggiar ein due direzione
- Quali connettori usare (Non protocollo, ma specifiche)
- Quali pin usare (La gran parte delle interfacce non indirizza tutti i pin, alcuni sono conservati per il futuro, in caso di ampliamento delle funzioni)
- Spara solo bit, corretti, velocemente, con basso rumore da non essere mal-interpretati
### Livello di collegamento data-link
- Gestire l'errore: se non riconosciamo subito il livello, ce lo portiamo appresso
- Organizza i bit in trame (centinaia o migliaia di byte): perché sappiamo dove inizia e finisce il messaggio: la trama, caricata nella scheda di rete viene confermata fino ad una conferma di corretta ricezione, in modo tale da essere pronti a reinviarla in caso di errori. La trama, gestita con destinatario, sorgente, dati e controllo
- Creiamo la trama individuando dei bit delimitatori di inizio e fine (esistono diverse tecniche)
- Ritrasmette le trame non pervenute o danneggiate (correggerla a destinazione diventa troppo pesante)
- La sorgente è veloce, il destinatario è lento: 1000 trame mandate per pochissime ricezioni. UItilizziamo quindi mediatori per rimediare a questo problema
### Livello rete
- Gestisce e controlla le operazioni di sottorete: protcollo di inoltro robusto. L'invio viene effettuato garantendo certezza dell'arrivo e della correttezza dell'arrivo. Poichè il nodo può avere più collegamenti, possiamo presupporre che, se un nodo va giù, dobbiamo garantire l'utilizzo di un'altro cammino
- Determinazione dei cammini sorgente-destinazione
- Gestione delle tabelle di instradamento: statiche (i percorsi sono stabiliti una volta e costanti) e dinamiche (i percorsi tra host sono gestiti controllando la libertà e disponibilità delle linee e delle porte instradando la comunicazione in linee o porte differenti a seconda delle necessità)
- Elemento essenziale governato da questo livello è il controllo della congestione: i protocolli di congestione si occupano di valutare quanto è l'incidenza della congestione - secondo le metriche di rete
- Enumerazione dei pacchetti: per garantire il corretto ordine dei pacchetti
### Livello trasporto
- I dati sono organizzati in segmenti, molto piccoli
- Possiamo avere un'eq tra connessioni di rete e di trasporto
- Possiamo avere n connessioni di rete su una connessione di trasporto (downward multiplexing: sommiamo canali per aumentare la mia capacità di connessione)
- Possiamo avere una connessione di rete su n connessioni di trasporto (upward multiplexing: ho un solo canale di rete su una macchina e mi collego a una sola macchina, ma a tante porte diverse, tante connessioni, utilizzando un solo canale)
### Livello di sessione
La sessione lavora "chi lavora e verso chi"
Il livello di sessione consente la contemporaneità e l'alternanza delle funzioni, attraverso sistemi di token e sincronizzazione
- Il livello di sessoine NON È presente nell'achitettura TCP/IP
### Livello di presentazione
- Non presente in TCP/IP
- Gestisce la sintassi e la semantica della macchina dell'utente, anche dal punto di vista linguistico
### Livello di applicazione
In TCP/IP assorbe anche sessione e presentazione

### Modello TCP/IP
Nel TCP/IP:
- lvl Applicazione assorbe Presentazione e Sessione
- Lvl Trasporto assorbe Trasporto e un po' di sessione
- Lvl Internet equivale a rete
- Lvl Link equivale a data link

### Livello Internet (IP) - Rete
- Commutazione di pacchetto su un livello privo di connessione (sono pacchetti datagramma - data telegram)
- È compito del destinatario riordinare i pacchetti
- Il livello si occupa di scegliere il cammino e evitare la congestione (presumiamo anche la perdita del pacchetto pur di non rallentare la connessione)
### Livello trasporto
- TCP: protocollo con connessione
- UDP: protocollo datagramma

### Livello Applicazione

### Efficacia modelli di riferimento
Paradosso di Clark
ISO/OSI - TCP/IP
L'ISO/OSI è nato dopo il TCP/IP, e nonostante gli sforzi di stnadrdizzazione TCP/IP era già uno standard de-facto

### Esempi di Rete
- ARPANET (Advanced Research Projects Agency NETwork): originalmente sotto il Dept. Of Defense, nel periodo della guerra fredda, per garantire lo scambio di informazioni sul sistema sistema missilistico in maniera velocissima e resiliente
- Nascono i primi router IMP (interface message processor): conservavano gli indirizzi di tutte le macchine della rete
- Nasce anche il DNS per associare alle macchine un nome simbolico
- ARPANET è rimasta in funzione fino agli anni '80 (gf112 era il numero di fenu su ARPANET, per capire quanta poca gente lo usava)

Quando nasce l'ISO/OSI, viene creato il modello tripla X (in ambito europeo). Nasce negli anni 70 in europa. Rete a pacchetto (dimensione 128/256 byte).
Circuito virtuale commutato (su tanti nodi, ne scelgo alcuni per attraversare la rete), circuito virtuale permanente: sembra una stortura, ma allora si aggiungono delle label per individuare delle connessioni utilizzate spesso

Frame relay: tanti nodi distribuiti in pochi posti del mondo. Funziona con l'indirizzo del singolo nodo. I servizi sono orientati alla connessione tra i singoli nodi, senza utilizzo di dorsali.

### Reti broadband - ISDN e ATM
ATM è una rete di commutazione con pochi byte, che non effettua il controllo degli errori. Sono usati pacchetti di 53 byte chiamati celle. È velocissima, per traffico costante, ma non è garantito il successo della consegna.

Il dato inviato, piccolissimo 48 byte, 53 byte di pacchetto
È interessante il modello di riferimento
Corrispondente al lvl 3/4 ISO/OSI -> Adaptation ATM Layer: livello che permette di adattare ATM a pacchetti TCP
Lvl 2/3 -> ATM: Flusso di controllo
1,2-> Livelli Fisici TC e PMD (Physical Medium Dependent)

### LAN Wireless: 802.11
