#Uni/Insegnamenti/Secondo_Anno/FPW 
# Parte 1 - come realizzare un sito web statico
- Il protocollo HTTP
- Il linguaggio HTML
- Le regole CSS

# HyperText Transfer Protocol

### Applicazioni web
Le applicazioni web 
Un'applicazione web statica è un'applicazione web dove, una volta create le pagine della applicazione web e, poste sul filesystem di un server, ogni volta che si chiedono le pagine web si otterranno le stesse informazioni, a prescindere dall'utente

Un'app web dinamica, funziona diversamente. Rimane uguale il funzionamento dell'accesso da parte dell'utente, ma il server si occuperà di confezionare la risorsa da fornire all'utente in maniera ad hoc al momento, a seconda del momento dell'accesso e dell'utente si otterranno informazioni diverse

Al giorno d'oggi i siti web statici sono molto pochi, un esempio tipico sono i siti "vetrina"

### Comunicazione client-server
Ogni volta che realizziamo un'applicazione web, abbiamo due attori, un client e server.
Il server è un computer che si trova da qualche parte e offre dei servizi, come le pagine web del sito.
Il client sono gli applicativi che accedono ai servizi offerti dal server; i client sono tipicamente i browser, ma anche tutte le applicazioni

Nel caso particolare del corso, client e server saranno sulla stessa macchina

### Browser web
È un programma su una macchina che permette di interrogare il server (client) e visualizzare (rendering) le risorse ricevute.
All'inizio dell'era internet, non tutti i browser erano uniformati sullo stesso standard, e risultava quindi molto complicato creare un sito che risultava uguale in tutti i browser

## Il protocollo HTTP
Il protocollo HTTP è l'insieme delle regole che permette a client e server di comunicare tra di loro.
La versione più utilizzata è HTTP/1.1 (1997-1999), e le versioni successive HTTP/2 e HTTP/3 sono comunque retrocompatibili

Originariamente internet era una tecnologia locale che permetteva di trasmettere (transfer) tra diverse macchine dei documenti (ipertesti)

Nonostante siano cambaite molte tecnologie, il protocollo HTTP è ancora il protocollo alla base dell'internet

Il protocollo HTTP è un protocollo di tipo domanda-risposta:
- Ad ogni richiesta del client corrisponde una risposta
- Sia nei casi di successo
- Sia nei casi di fallimento

È un protocollo senza stato (**stateless**), ovvero che gli scambi di comunicazione tra client-server successivi non sono dipendenti dalle comunicazioni precedenti. Per ovviare a questo problema si sono costruite delle altre tecnologie (come i cookies)

Le richieste HTTP viaggiano su un protocollo di trasporto che non è oggetto di questo corso e garantisce la consegna sia della domanda che della risposta. All'interno dello stesso canale TCP è possibile far viaggiare più richieste HTTP

### Richiesta HTTP
All'interno di una richiesta HTTP includiamo un URI, che identifica in maniera univoca la risorsa richiesta
Si specifica un metodo
Metodo:
- GET
- POST
- HEADER
Degli Header

### Risposta HTTP
- Codice di stato e frase di stato: sono utilizzati dal server per fornire ogni volta una risposta e contengono informazioni sullo stato del servizio
	- I valori 2xx indicano successo
	- I valori 3xx indicano un reindirizzamento della richiesta su un altro server
	- I valori 4xx indicano un errore client-side
	- I valori 5xx indicano un errore server-side

### Cookies
I cookies sono delle coppie chiave-valore matenute fra più comunicazioni tra client e server
Cin la prima risposta il client riceve un valore associato a una chiave che lo identifica

## Cenni sulla sicurezza

## URL - Uniform Resource Locator
`<protocollo>://<nomehost>:<porta>/<percorso>?<querystring>#<fragment>`
- Protocollo: è l'applicativo da utilizzare per reperire la risorsa descritta
- Nome host: costituito da un nome di dominio o da un indirizzo IP
- Porta: da specificare solamente quando si utilizza una porta non-standard
- Percorso: path locale della risorsa richiesta all'interno del server
- Query string: serie di coppie nome-valore, utilizzati dal server come parametri
- Fragment: viene utilizzato per specificare una posizione specifica all'interno di una risorsa
- 