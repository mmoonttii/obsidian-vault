#Uni/Insegnamenti/Secondo_Anno/RC 
# Reti radio mobili
Dai 900 MHz ai circa 5 GHz
### Differenza tra reti raido mobili e sistemi cellularu
Dato che questa comunicazione sarebbe generalmente broadcast
Abbiamo molte frequenze in una stessa cella: molti provider e molti utenti. Abbiamo quindi il problema del riutilizzo delle frequenze

### Riutilizzo delle frequenze
Prendiamo l'intervallo di frequenze e ipotizziamo di crearne dei cluster.
Per sfruttare al meglio le celle riutilizziamo le stesse frequenze in modo da sfruttarle più volte. Distribuiamo sull'intero territorio le diverse frequenze mantenendo il cluster, facendo in modo che non si siano celle limitrofe con frequenze uguali
Le celle hanno dimensioni dipendenti dalla potenza trasmissiva, poichè abbiamo antenne piccole dobbiamo dosare le potenze per trasmettere adeguatamente ma in maniera sicura per la salute. Il raggio massimo di una cella sarà quindi di circa 35 km

La trasmissione wireless avviene solamente dall'antenna verso i dispositivi, mentre tutto il resto del collegamento è cablato.

Per questioni di orografia difficili o ostacoli fissi la forma di una cella non è regolare.

Sulle celle abbiamo bisogno di consentire lo spostamento di un utente da una cella a un'alòtra senza che venga percepito il cambio di canale.
PEr ogni cella pgni *base station* ha a disposizione un certo numero di canali.

- riducendo le celle aumenta il numero di utenti, ma diminuisce la _distanza di riuso_ delle frequenze e aumentano gli handover (QoS): la struttura di ogni cella è quindi molto variabile a seconda del territorio

## Sistemi cellulari analogici
Basato sulla variazione di potenzaile
- Ad ogni utente viene assegnata una frequenza per l'intera durata della conversazione: se una frequenza è disturbata non è possibile cambiarla per avere una comunicazione migliore
- non e' possibile applicare sistemi di crittografia ( se non scramblerm, perchè non è numerico)
- sicurezza di trasmissione basata solo sul riconoscimento del terminale mobile, non esiste un modulo come la sim
- Questa tecnologia non è adatta alla trasmissione dati

### Prime applicazioni
- TACS: 890-960 Mhz (1000 canali in 70 Khz) 25+45 Khz
- E-TACS: 872-950 Mhz (1320 canali in 78 Mhz) 25+34 Khz (la dimensione del canale diminuisce)
- Sono però limitati all'uso nazionale (apparati differenti, mancata interoperabilità e concorrenza)

### Sistema GSM
- Basato sulle stesse frequenze (intorno alle 900 MHz), ma in maniera digitale (numerica)
- QoS
- Basso costo di terminale (costo generale sulla struttura)
- basso costo di gestione (controllo di scala)
- compatibilita' ISDN (comunica come su ISDN)
- roaming internazionale (non siamo limitati sulla gestione delle frequenze a livello nazionale)
- sicurezza e riservatezza comunicazioni (è possibile controllare, replicare, crittografare e verificare le comunicazioni)
- impiego di tecniche TDM aggiuntive (possiamo usare uno stesso canale per 8/16 slot e relativi utenti)

- frequenze riservate al GSM:
	- 890-915Mhz up-link (25Mhz) - da terminale a base station
	- 935-960Mhz down-link (25 Mhz) - da station a terminale
	- massimo sfruttamento della banda 25 Mhz nella service-area (area dove utilizzo un dato cluster di celle) col riutilizzo delle frequenze

Caratteristuche peculiari
- È il primo sistema standardizzato
- compatibilita' totale ISDN e OSI
- Roaming internazionale
- È possiblie la trasmissione dati (senza impiegare sistemi modem)
- Possiamo usare Short MEssage System

Questo sistema poco dopo essere uscito portò alla saturazione delle celle
- Non potevamo stringere ulteriormente i canali prima di raggiungere un limeite strutturale

### DCS 1800 (evoluzione del GSM)
Le frequenze sono adesso a cavallo dei 1800 MHz
 - Usa il protocollo PCN
 - Caratteristuche di propagazione differenti (frequenza più alta => i fenomeni di assorbimento aumentano)
 - Ampiezza di banda tripla 75 Mhz che triplica gli utenti per cella, da SOMMARE a quelli dei 900 MHz
 - Minor potenza di trasmissione

A questo punto abbiamo bisogno di dispositivi multi standard
- Dual band: stessa tecnologia ma frequenze differenti spesso con 
- Dual mode: diverse tecnologie: (GSM - DECT o GSM - satellitare)
- Dual sim

Caratteristuche tecniche 
ipotesi di suddivisione del territorio con banda 25Mhz e 1 canale da 200Khz
- N = 25Mhz/200Khz = 125 canali contemporanei
- con 3 sottobande N/3 = 41 canali per sottobanda
- con service area di 11 celle avremo: 41\*11 = 451 *canali contemporanei*
all’aumentare delle celle si rischia _l’interferenza cocanale_

_ritardo di propagazione_ tra BS - ME – BS e max dim. cella:
- tempo massimo consentito di comunicazione (max ritardo) 233 microsec
- 233\*10^-6 (sec) 300.000Km/sec = 70 Km dunque BS-ME e’ pari a 35Km

maggior sfruttamento della banda:
- al diminuire della dimensione della cella si rischia l’interferenza cocanale
- al diminuire della potenza trasmissiva si abbassa QoS

Tecnica di accesso mista: 
- Abbiamo diviso le frequenze
- Per ogni frequenza abbiamo diviso in 8 o 16 timeslot
canale 200 Khz pari a 174 portanti
- con campionamento 16Kbps (full-rate) 1392 canali
- con campionamento 8Kbps (half-rate) 2784 canali

Con DCS 1800
1755-1785 Mhz 30Mhz complessivi
1850-1880 Mhz 30Mhz complessivi

canale 200 Khz pari a 150 portanti
- con campionamento 16Kbps (full-rate) 1200 canali
- con campionamento 8Kbps (half-rate) 2400 canali

### Suddivisione per elementi architetturali del sistema GSM

MS (Mobile Station) = ME (Mobile Equipment) + SIM (Subscriber Identity Module)

- IMEI (International Mobile Equipment Identity) = TAC/FAC/SNR/sp
	- 6cifre modello e costruttore
	- 2 cifre luogo di costruzione
	- 6 cifre serial number
	- 1 cifra disposizione/usi futuri
- SIM: contiene processore (16 bit) esegue algoritmi di cifratura e memoria
Questi elementi permettono di riconoscere sempre da quale dispositivo e quale utente sta comunicando
codici associati primari (al sottoscrittore dell'apparecchio):
- IMSI, (International Mobile Subscriber Identity)
- K_i chiave di autenticazione
Altri codici secondari permettono cifratura, autenticazione, etc
- A8, algoritmo di cifratura
- A3, algoritmo di autenticazione
- PIN, PIN2
- PUK (PIN Unlocked Key), PUK2
- rubrica telefonica (text/voice), SMS, MMS, EMS, lista operatori

Per un periodo la comunicazione era così efficiente che si è introdotto un cosidetto "rumore di conforto" per assicurare l'utente che la comunicazione fosse in atto

## Architettura GSM
BTS: Base transceiver station
Un grippo di antenne finiscono su un base station controller
Più base station coporono il territorio e sono gestite dal Mobile Switching Center
All'MSC è sempre associato il VLR che registra in quale area si trova un utente
Se non si trova nel VLR, il MSC "indaga" per trovare in quale BSC si trova l'utente, cercando nel HLR (dove si trovano dati dell'abbonato, dei servizi attivati e l'ultimo VLR su cui è stato registrato)
A questa rete sono connessi dei Gateway per le altre reti come PSTN, ISDN o dati, ma anche per un altro provider.
L'intera struttura è gestita dall'OMC (continuativo) e NMC (in caso di guasti)

Nel'EIR, per ogni instaurazione di comunicazione, sono contenuti record di ME:
- Con IMEI omologati (white lsit)
- Con IMEI non omologati (gray list)
- Con IMEI bloccati (blacj list)

Nell'AuC sono registrati :
- _
- _

L'OMC controlla e gestisce
- gestisce le configurazione e le prestazioni di tutti gli elementi dell’architettura (BTS, BSC, MSC, VLR, HLR, AuC, EIR);
- gestisce guasti, allarmi, stato del sistema;
- programma ed esegue test periodici;
- raccogli tutti i dati per l’accounting degli utenti.

Il NMC controlla e gestisce gli OMC e entra in funzione in caso di guasti

### Multiplexing TDMA
Ogni canale 200 Khz è suddiviso in frame da 4,616 ms
Ogni frame è suddiviso in 8 time-slot da 0,577 ms

I timeslot generano 26 frame (120 ms) che formano una TRAFFIC MULTIFRAME
Nel numerico, i dati di controllo, sono quadi quanto i dati trasmessi: 51 frame (235 ms) formano un CONTROL MULTIFRAME
Una TRAFFIC SUPERFRAME (6,12 s) è formata da 51 CONTROL MULTIFRAME
Un CONTROL SUPERFRAME (6,12 s) è formata da 26 CONTROL MULTIFRAME
Una HYPERFRAME (3h 28m 53s) è formata da 2048 SUPERFRAME

_Ogni comunicazione_ è caratterizzata da:
1. Numero di time-slot (TS) assegnato
2. Numero di trama (FN) calcolato sull’ HYPERFRAME
3. Numero frequenza della portante (canale radio usato)

Per consentire l’handover, una stessa comunicazione ha il time-slot di TX shiftato di 3 time-slot rispetto a quello di RX

## Difficoltà della comunicazione
- Interferenza cocanale (celle limitrofe)
- Fading (evanescenza momentanea):
	- riflessioni d’onda su piu’ superfici riflettenti (fading veloce);
	- assorbimento dovuto ad ostacoli di grande dimensione maggiori della lunghezza d’onda (fading lento).
	- Per evitare questi fenomeni nelle città abbiamo celle più piccole
	- per ovviare esistono due tecniche:
		- antenna diversity: si pongono due antenne riceventi a distanza λn;
		- frequency hopping: la comunicazione viene trasmessa su due frequenze diverse

## UMTS - 3G
3 GHz
Usa FDM e TDM creando l'ipertrama, puntantdo a velocita’ di trasmissione dei dati tra 384Kbps e 2.048Mbps (144 Kbps per terminali mobili a velocita’ di 500 Km/h), ma anche tecnologia soft-handover che elimina le discontinuita’ registrabili nel passaggio di cella (1885-2025 Mhz e 2110-2200 Mhz).

### Soft-handover
Si innesca il meccanismo di passaggio mentre si ha ancora attiva la comunicazione sulla cella precedente.
