#Uni/Insegnamenti/Secondo_Anno/RC 
# Standardizzazione delle reti
>  Uno standard è 

In ambito tecnologio ha un'importanza strategica
Non è un semplice documento, ma un insieme di specifiche
Il processo coinvolge enti nazionali, privati ...

Vantaggi della definizione di uno standard

Esistono due tipologie fondamentali di standard:
- Standard de facto
- Standard ex lege

## Enti di standardizzazione
Esistono diversi enti, ciascuno con ambiti e competenzee specifiche

### Standard di telecomunicazione
ITU, agenzia ONU, si occupa di ...

### Standard internazionali
In generale
- ISO
- NIST
- IEEE

### ITU
...
L'ITU lavora per garantire l'interoperabilità tra sistemi di telecomunicazione differenti
È suddiviso in tre sezioni

ITU-D: per supportare l'espansione delle tecnologie in paesi più arretrati
#### ITU-R
#### ITU-T
Definisce standard 
#### ITU-D
Meno tecnica, ma più sociale e inclusiva

### ISO
Dall'idea allo standard ISO

### IAB

Rinnovato a fine anni 80 e organizzato in IRTF IETF e ISOCù
ù

#### Altri
- NIST
- IEEE

# Mezzi trasmissivi guidati
Utilizzano un mezzo fisico per la trasmissione del flusso grezzo di bit
È caratterizzato da
- Banda passante: dati che possono essere trasmessi in un dato intervallo di tempo
- Ritardo: tempo per percorrere il mezzo
- Costo
- Installabilità: facilità di posa/opera
- Manutenibilità: facilità di intervento in caso di guasti/aggiornamenti

## Doppino
Indica una linea di trasmissione composta da una coppia di conduttori di rame siolati, pensato inizialmente per la trasmissione telefonica adottato poi da Ethernet

I due conduttori sono intrecciati per elidere i campi elettromagnetici creati dai due conduttori.

Per il protocollo ethernet sono organizzati in 4 coppie e terminati con un connettore RJ-45

### Schermatura
Oltre alla torsione del cavo, per ridurre l'impatto delle interferenze

La schermatura è composta da un conduttore metallico che agisce anche da messa a terra:
- Esterna
- Interna

Sono caratterizzati anche dalla lunghezza massima del mezzo e sono categorizzati

#### Tipologie di schermatura
- UTP
- STP
- S/UTP
- S/STP

Categorizzazione UTP in base al cablaggio: standardizzazione effettuata dalla TIA/EIA
- Cat. 3
- Cat. 5
- Cat. 6 e 6a
Alcune categorie non riconosciute
- Cat. 1
- Cat. 2
- Cat. 4
- Cat. 7 e 7a

## Cavo coassiale
Noto per il trasporto dei segnali radiotelevisivi, adattato successivamente alla comunicazione digitale

Rispetto al doppino:
- è molto più schermato
- Distanze maggiori
- Distanze piu elevate

Esistono due tipologie di cavo coassiale
- 50 ohm: usato per trasmissioni digitali
- 75 ohm: usato per segnale video analogico

Caratteristiche del cavo coassiale
Costruzione e schermatura: garantisce ampiezza di banda e immunita al rumore
La banda passante dipende dalla qualità dei materiali, lunghezza del cavo, rapporto segnale/rumore
Il cavo coassiale è impiegato per reti metropolitane e televisione via cavo

## Fibra ottica
Re dei mezzi condotti

### Sistema di comunicazione ottico
1. Invio segnale elettrico
2. Modulato in segnale lunminoso
3. Il segnale luminoso transita sul caanle
4. Il demodulatore riconverte il segnale luminoso in elettrico
5. La destinazione riceve i dati elettrici


### Come non viene dispersa la luce
Se l'angolo di incidenza della luce su lvetro è minore dell'angolo critico, questo verrà riflesso all'interno della fibra.

### Struttura di una fibra ottica
- Core
- Cladding
- Rivestimento
- Irrobustimento
- Guaina esterna

Le fibre si distiguono per il diametro del core

### Tassonomia
Fibre monomodali: un solo raggio per volta
Fibre multimodali: più raggi percorrono la fibra contemporaneamente
 ( i diversi modi possono essere rallentati in amniera differente, questo porta a una diminuzione di qualità)

# Mezzi trasmissivi non guidati

## I fondamenti della trasmissione non guidata
Nal 1865 con MAxwell le onde elettromagnetiche.

Le onde elettromagnetiche

Lo spettro elettromagnetico

### Utilizzo delle onde elettromagnetiche:
Modulazione di:
- Frequenza
- ampiezza
- fase


## Tipologie di trasmissione non guidata
- Trasmissione a banda ristretta: miglior ricezione, concnetriamo tutta la potenza in una banda di frequenze limitate
- Trasmissione a banda larga: spettro distribuito a frequenza variabile, spettro distribuito a frequenza diretta

## Onde radio
Semplici da sviluppare èer la loro bassa frequenza
Omnidirezionali (non è necessaria line of sight), ma meno potenza e più soggetta alle interferenze
Le diverse proprietà dipendono dalla frequenza:
- Alte frequenze VHF
- Basse frequenze VLF: il segnale viaggia più facilemente attraverso gli ostacoli e in maniera omnidirezionali, ma perdono freqnza più velocemente

Più un segnale arriva lontano, maggiore è la possibilitò che disturbi altre onde o venga intercettata

## Microonde
È necessario che le antenne siano allineate

## Infrarossi
Onde THF
Maniera direzionale
Basso raggio

## Onde luminose
Segnali ottici, visibili a occhio nudo
Unidirezionali, dacilmente disturbabili, 
Facili da installare, costo ridotto, nessuna licenza: grande precisione e quindi poco utilizzate