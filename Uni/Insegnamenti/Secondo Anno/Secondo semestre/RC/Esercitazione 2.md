#Uni/Insegnamenti/Secondo_Anno/RC #Uni/Tutoraggio/RC 
# Software di Rete
### QoS
Im servizio si dice aggifabile quando: si propone di non perdere mai i dati, richiede eche il ricevente incvvii una conferma, introduce un aumetno del traffico di rete
### Tipologie di Servizi
--- immagine sul cellulare ---

## Primitive di servizio
Ogni livello offre delle funzionalità base al livello successivo
Il servizio è specificato attraverso una serie di primitive, ovvero operazioni semplici.
Ogni livello implementa un set base di questi tipi, però possono aver enomi e modalita digfertenti, e primitive dipendenti dalla classe di servizio che viene offerta
Listen: attesa vloccante
Connecr
Receive
Send Manda
Disconnect Termina

### Caratterizzazione
Ciascuna primitica può implementare dei metodi che permettono di fiormire differenti qualità del servizio
--- foto sul telefono --- req (), ind (), res (), con ()

### Utilizzo generico di primitive
A intende instaurare unaconnessione orientata e affidabile con V
A invia request () da n a n-1
B riceve indiciation () da n-1 a n
B incia response () da n a n-1
A riceve conferm () da n-1 a n

## Comunicazione client-server
-- I sul tel--
-- chiedere a chiara II e III --

### Socket di Berkley (che hanno fatto in maniera troppo approfondita)

### Relazione tra protocolli e servizi

# Modelli di riferimento
Arch di rete indentifica un insieme di livelli e per ciascu livello i protocolli da usare
Modello di rig identifica numero, reklzione e caratteristiche dei livelli, ma non i protocolli

--foto tel differenze progettuali--
## Modello ISO/OSI
7 Livelli, teorico e ben strutturato
## Modello TCP/IP
4 livelli, derivato dall'implementazione pratica delle reti. Più snello
# Esempi di rete
## Reti X.25
Garantire affidabilità su reti non ottimali
Pacchetti di dimensione fissa, ma suddivisione header/dati variabile

## Reti frame relay

## Reti ATM
Asyncronous Transfer Mode

### Modello di rfiferimento delle reti ATM

## Reti RFID
Si possono varatterizzare in base alla fonte di energia, in base alla frequenza di lavoro
Diversi problemi