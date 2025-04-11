#Uni/Insegnamenti/Secondo_Anno/RC 
# Il livello fisico
## Basi teoriche delle comunicazioni di dati
### Analisi di Fourier
L'analisi di Fourier è una funzione periodica, con periodo T, può essere ottenuta sommando funzioni seno e coseno (serie di Fourier): con an e bn sono ampiezze della n-esima armonica
$$
g(t) = \frac{1}{2} c \sum_{n=1}^{\infty} a_{n} \sin(2\pi nf(t)) + \sum_{n=1}^{\infty} b_{n} \cos(2\pi nf(t))
$$
### Segnali a larghezza di banda limitata
- nessun mezzo trasmissivo e’ in grado di trasmettere senza perdita di potenza
- ogni componente di Fourier subisce attenuazioni differenti a seconda del mezzo trasmissivo impiegato
- La banda trasmissiva può derivare dal mezzo o può essere **introdotta** artificialmente

- la trasmissione delle frequenze più basse può comportare la trasmissione della prima armonica (fondamentale). 
- all’aumentare della frequenza aumenta il numero delle armoniche trasmissibili
- il segnale trasmesso e’ in funzione dei cambiamenti al secondo (ad es. voltaggio) che si misurano in baud.
- un baud, a seconda della quantita’ di segnali rappresentati, puo’ trasportare piu’ bit alla volta 

### Tasso di dati massimo per un canale
L'assenza di rumore non esiste.
Il teorema di Nyquist teorizza un canale senza rumore, dove la massima banda è data da $2H\log_{2}V\ bit/s$

Si può definire il rapporto $S/N$ segnale/rumore espresso in $10 \log_{10} S/N$, misurato in $dB$

La formula di Shannon invece calcola la massima banda di un canale con rumore

## Mezzi di trasmissione con mezzo condotto
### Doppino telefonico
Twisted pair: perchè abbiamo delle coppie di cavi
Abbiamo 4 coppie di cavi
Non sono altro che fili di rami, ritorti per evitare l'effetto antenna l'uno dell'altro

Seguono, ovviamente, la legge di Joule, in categoria 5e, queste perdite non sono significative fino a 100 m

Dopo 100 m abbiamo perdita del segnale, quindi abbiamo maggiore ritrasmissione di pacchetti etc.

### Cavo coassiale
- Impedenza 50 ohm: Adatto a comunicazioni digitali, su distanze di 1 km con velocità fino a 2 Gbps
- Impedenza 75 ohm: Adatto a comunicazioni analogiche, cavo tipico dell'architettura ATM e utilizzato per la TV via cavo. In questo caso possiamo aver due tipi di segnale, utilizzando il cavo half-duplex, o in full-duplex dividendo la banda in due sezioni, una per direzione

#### SDH - Synchronous Digital Hierarchy
B-ISDN 64 kbps è perfetto per un canale fonico
STM-1: questo sistema serve per inviare contemporaneamente più comunicazioni in un solo invio
STM-4: 622.08 Mbps
STM-16: 2.5 Gbps

A Cagliari abbiamo 15 centrali che sfruttano questa struttura (uno dei primi posti a farlo)

### Fibre ottiche
La fibra è un mezzo condotto composto da uno strato interno **core**, purissimo, e uno strato **cladding**, meno puro intorno.
Se il core è abbastanza stretto, l'impulso luminoso viaggia velocissimo senza rumore, perdita di calore o altre variazioni, quindi riesce a viaggiare per chilometri.
Aumentando la sezione del core, diminuisce il costo, diminuisce anche la velocità. 
I problemi delle fibre è la conversione tra impulso luminoso e elettromagnetico e la connessione tra due fibre (perdita circa del 10/20% del segnale)

Il sistema di trasmissione è monodirezionale, normalmente le fibre si posano in gruppi da 8 (4 comunicazioni bidi)

La fibra può essere illuminata con un LED (più economico e meno preciso) o attraverso un laser (molto più costoso)
![[Pasted image 20250324175014.png]]

Le fibre ottiche possono avere il segnale ripetuto o splittato

Dato un range di frequenze di luce disponibili, si trasmette solamente in alcune bande, dove l'attenuazione della luce è più bassa
$\text{attenuazione della luce} = 10 \log_{10} {E_{trasmessa}}/{E_{ricevuta}}$

> 10 domande: 5 risposte possibili, 1 correttta
> - Non rispondere -> 0
> - Rispondere sbagliato -> -0.25
> - Rispondere corretto -> 0.5
> 10 giuste -> 5 pt
> 3 domande a risposta aperta (definizioni, ragionamenti, spiegare un'architettura): scrivere abbondantemente - Introduzione, entrare nell'argomento, considerazioni personali o integrazioni
> 2.5 pt per ciascuna domanda aperta, punteggio negativo se si scrivono cavolate
> Up to 12.5/12.5
> 08:45 primo turno 09:20 secondo turno

## Trasmissione senza fili (senza mezzo condotto)
Nei  mezzi gia visti, dove l'impulso corre attraverso il mezzo, abbiamo la velocità, ma lo svantaggio di dover posare il mezzo fisico.
I mezzi non condotti, hanno la possibilità di avere una distribuzione multidimensionale
Le comunicazioni avvengono in una gamma di frequenze differenti e possono essere inviate contemporaneamente con tecnologie differenti.

>  Generalità dello spettro elettromagnetico

Ci occupiamo dalle onde transoceaniche, lunghissime, alle onde più piccole come i raggi 
### Spettro elettromagnetico
Partendo dalla definizione di Maxwell di elettroni in movimento
- ƒ frequenza: numero di pscillazioni
Le antenne hanno dimensione inversamente proporzionale alla frequenza
-  $\lambda$ lunghezza donda, distanza tra due massimi
La velocità delle onde elettromagnetiche è costante: $c = 3\cdot 10^8$ 
$$
\lambda f = c
$$
L'ITU assegna le frequenze in un determianto modo
- Le prime onde, a bassa frequenza (30-300 kHz), la ha chiamate Low frequency
- (300-3000 kHz) Medium Frequency
- (3-30 MHz) High frequency

Nello schema sono sovrapposti alla frequenza i mezzi che possiamo utilizzare per questo
Sono state poi scoperte utilizzabili onde con frequenze ancora più elevate
- VHF (Very): radio
- UHF (Ultra ): tv
- SHF (Super): satelliti
- EHF (Extremely)
- THF (Tremendously)

In questo spazio possiamo utilizzare un sistema per intercettarle, fino ai Giga abbiamo un rapporto 1:1 tra frequenza e velocità di trasmissione
Ogni trasmissione elettromagnetica è una trasmisssione che genera potenza
> Spiegare lo schema delle frequenze

  L’informazione trasportabile (bit) e’ in funzione della larghezza di banda:
- e’ pari alla larghezza di banda per basse frequenze;
- il rapporto aumenta per le alte frequenze.
Queste assegnazioni di frequenze sono fatte dall'ITU-R
Le freq tra 80 e 120 MHz sono frequenze radio in quasi tutti i paesi
Ogni volta che un segnale è emesso esprimiamo potenza, quind possiamo definire un rapporto potenza emessa/frequenza: è quindi meglio trasmettere con uana frequenza ristretta

Per ridurre i "problemi ?" spesso si utilizzano alcuni algortimi come quelli a salto di frequenza o a banda larga per ridurli

### Trasmissione radio (30 - 200 MHz)
A bassa frequenza hanno un decadimento di potenza di $\frac{1}{r^2}$
Con le alte frequenze si possono creare riflessioni su edifici o sulla ionosfera per aumentare la distanza, perchè aumenta l'assorbimento

### Microonde (100 MHz - 10 GHz)
La frequenza è più stretta, l'allineamento più marcato, ma le antenne devono essere in vista.
Qualsiasi ostacolo causa assorbimento
$d = \sqrt{ h 10^4 a }$ indica che la distanza massima è intorno ai 10 km
Attorno agli 8 GHz l'interdernza per lambda è di pochi cm

Dalle microonde in poi si genera un affollamento delle frequenze: più operatori e poiù segnali voglioni trasmettere

### Infrarosso e millimetriche (10 - 100 GHz)
L'infrarosso non attraversa i mezzi fisici e quindi normalmente non è usato in spazi apertiù

### Trasmissione a onde luminiose
Laser, ma il semplice calore emanato dal tetto può far variare l'allineamento

### Comunicazioni satellitari
> Tipologie di satellitari

- Satelliti geostazionari (36000 km)
- Satelliti su orbite medie (15-5 000 km)
- Satelliti su orbite basse (5000 km - )

Si chiamano **impronta del satellite** le aree che il satellite copre. L'ìarea è maggiore, maggiore è l'altitudine. Minore è l'altitudine più satelliti servono

Starlink ha un orbita bassissima (500-1000 km) e quindi ne deve mandare un numero enorme per coprire l'intero globo 

I satelliti geostazionari sufficienti per coprire tutto il globo sono 3, la latenza (tempo per comunicare) è 270 ms a cui bisogna sommare il tempo per la trsduzione ottica
Portare in orbita un satellite costa un sacco di soldi

GPS (controllato dagli USA) 1-5 m, Galileo (EU) 30 satelliti 10 cm

Prima o poi un'orbita si riempirà e ci dovremo attrezzare

È necessario evitare le "Fasce di Van Allen", delle fasce molto elettromagnetiche che circondano la terra e rischiano di interferire con il segnaleù

Satelliti VSAT con HUB: permette di invire al satellite e ripetere il segnale con un'antenna a terra per raggiungere un altro satellite
Il sistema global star è utilizzato per molte comunicazioni, anche militari e sono vari, anche precisissimi. Posson anche registrare immagini precisissime e nitidissime
"Il meraviglioso mondo di Tanenbaum" ~ G. Fenu

## Il sistema telefonicp
PSTN, sistema di partenza, ancora alla base del sistema moderno per non riposare la rete da zero
Il sistema ha un sistema a maglia su tutto il territorio
- UCR (migliaio di utilizzatori, ridondato al ~20%)
- CU (migliaia di utenze), può quindi anche coprire aree più ampie di un comune - a Cagliari abbiamo circa ~15 CU
- Più CU o CRU convergono su una SGU (prima centrale che vede il resto della rete)
- Si connette alla SGT e alla CN
Un SGU può essere nello stesso locale del SGT e più SGT (di diversi provider) possono essere connessi

-- Nel disegno di Fenu, il bianco è il detentore della rete --
C'è un unico caso dove gli utilizzatori di reti altrui raggiungono le abitazioni: 

Circuito locale (analogico)
SGT accetta sia segnale voce che segnale dati

Passaggio analogico-digitale: comporta attenuazione del segnale, rumore

Teorema di Nyquist
Misurati i bit/secondo su un'armonica, possiamo aumentare le armoniche su un doppuni

Sistema DSL:
Poichè il doppino è dappertutto si sono utilizzati metodi per ceracre di sfruttare la rete esistente, in oarticolare il problema dell'ultimo miglio: si prova a sfruttare lo stesso doppino per internet e telefonia: sistema DSL
Poichè un utente medio è più probabile abbia da scaricare che da caricare abbiamo ADSL
Abbiamo 256 canali da 4 kHz (dimensione canale fonico di base): uno è dedicato alla voce, uno di spazio e 254 per dati

Sistema FTTH:
Anzichè canali diversi, abbiamo \lambda differenti

Multiplexing
FDM: ogni canale copre una porzione
WDM: ogni canale ha uno spettro
TDM: ogno canale ha uno sp

PCM:
T1 (USA) 1.544 Mbps; E1 (EU) 2.048 Mbps

Modulazione a codice di impulso differenziale

Multiplexing
Più T 1 convergono in un T2, tanti convergono in un T3, tanti in un T4

Questo sistema, dove unisco tante comunicazioni che vengono unite e splittate solo a arrivo e destinazione: Plesiocrona

Sincrona: durante il percorso può caricare altre informaizoni, ottimizzadno la matrice

# Principi di commutazione
ISDN
Utilizzo delle linee tradizionali per voce e dati
Porzione minima di dati digitali 8000 campionamenti a secondo, 8 bit a campionamento = 64 k canale minimo di comunicazione
Interfacce U, T e S

Canali utilizzati
B: 64 kbps (voce/dati)
BRI: base rate interface 2B+D due canali fonici più uno di segnalazione

PRI: 30 canali più due di controllo  30B+D: 2048 Mbps

B-ISDN
Circuiti virtuali permanenti
Circuiti virtuali commutati

La trama PCM utilizza time-slot che si ripetono ciclicamente

ISDN invia sempre anche cose vuote, ATM solo quando ha cose da inviare > più efficiente. ISDN è più sicura (effettua controlli)

# ESAME
Turno 1: 8:45 a Palazzo - 9:00 inizia il compito
Turno 2: 9:25 a Palazzo

- 10 domande a risposta chiusa (5 risposte, 1 corretta) - consiglio di non cambiare in continuazione
- 3 domande aperte: definizioni, processi, ragionamenti: inquadrare problemi, illustrarlo, conclusioni

Bisogna lasciar scadere il tempo

Turno 1
Didu
Ghironi
Guerrini

Turno 2
Montalto
Pala
Ruiu

Secondo preappello: sabato 10 maggio