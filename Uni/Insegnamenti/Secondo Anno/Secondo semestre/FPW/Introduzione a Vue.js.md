#Uni/Insegnamenti/Secondo_Anno/FPW 
# Web application
I tre pilastri della programmazione web sono:
- Client (browser)
- Server
- Database
Non avremo mai client e database che comunicheranno tra di loro
Il client è responsabile di presentare l'interfaccia utente, inviare richieste al server per ottenere o inviare dati, è solitamente sviluppato utilizzando linguaggi come HTML e CSS, o framework basati su JS come Vue.js, React e Angular
Il server si occupa dell'accesso al browsere per recupero o memorizzazione di dati, coordina tutte le attività, utilizzeremo Node.js che permette di usare JS per scrivere il backend
Il database che useremo è PostgreSQL

I linguaggi che vedremo sono HTML, CSS, JS e SQL

# Vue. js
Vue è un framework JS, basato su HTML, CSS e JavaScripr
Fornisce un modello di programmazione dichiarativo, basato su componenti, per sviluppare in modo efficiente interfacce di qualsiasi cmoplessità
- DOM
- È un linguaggio basato su componenti: è suddiviso in sezioni modulari, organizzando il codice e rendendolo più gestibile
Vue ha molte funzionalità, ma noi ne sceglieremo solo alcune

## Panoramica di un progetto Vue
- `package.json` contiene informazioni sul progetto come nome, versione, scripts e dipendenze
- `index.html`: punto di ingresso HTML, contiene `<div id="app"></div>`, che è il punto dove viene inserita la nostra pagina vue
- `src`: cartella che contiene i sorgenti
- `vite.config.js`: per connettere backend e frontend

All'interno di `src` avremo
- `assets`: risorse statiche
- `components`: contiene gli SFC che rappresentano i componenti
- `router`: contiene la definizione delle route
- `stores`: 
- `views`:
- `App.vue`: è il componente Vue principale
- `main.js`: è il punto di ingresso del codice JavaScript dell'intera applicazione

Questa è la cartella del client

# Modello di programmazione basato su componenti
Un'app Vue.js è suddivisa in componenti con estensione `.vue`
Sono realizzati con un formato simile all'HTML, chiamato SFC (single file component)
Un SFC, incapsula la logica (JS), il modello (HTML) e gli stili (CSS) del componente in un unico file

I componenti Vue, sono i mattoni per progettare le interfacce web e possono essere riutilizzati e incorporati in componenti di livello superiore per ottenere il layout desiderato. Possiamo assimilarli ad una struttura ad albero.
Anche le pagine stesse sono dei componenti, nonostante vadano inserite nella cartella `views`.

Per collegare i componenti tra loro, i componenti figli vengono dichiarati nel template del componente padre

I componenti possono
1. Essere pagine (views)
2. Componenti che si ripetono nella stessa pagina
3. Componenti comuni a più pagine, nella stessa posizione
4. Componenti in più pagine, ma in posizione diversa

I componenti del tipo 3 si importano in `App.vue`
Al posto di `<RouterView />` verranno visualizzati i componenti del tipo 1
Gli altri componenti si importano all'interno delle `view` e dei `components`

### Albero gerarchico dei componenti
- App.vue
	- RouterView
		- Home
		- Products
			- Product
			- Product
			- ...
	- NavBar
	- Header
	- Footer
	- Advs
		- Adv
		- Adv
		- ...

# Gestire manualmente le manipolazioni del DOM
Vue ci permette di creare dei siti dinamici senza dover andare a manipolare manualmente il DOM
## DOM
Il codice JavaScript si può aggiungere a una pagina HTML con il tag `<script></script>`
La pagina HTML viene rappresentata come un albero
- La radice è il nodo HTML
- Tutti gli altri nodi rappresentano gli ellementi della èagina HTML
- Rappresenta in modo diretto la struttura gerarchica
Il DOM è una rappresentazione ad oggetti della struttura ad albero della pagina HTML
Questa rappresentazione permette di accedere e aggiornare dinamicamnete il contenuto, la struttura e lo stile dei documenti con JavaScript

## Document
La classe document di JavaScript ha funzioni per creare nuovi nodi dinamicamente, per cercare nodi di base ...
- Node rappresenta un nodo del documento HTML

# Pattern MVVM
## MVC
Una volta che abbiamo un'applicazione che viene spesso modificata, la manutenzione diventa sempre più difficile e complicata.
Si è pensato quindi di dividere il codice in blocchi
- Model
- View
- Controller

## MVVM 
È il metodo usato da Vue
Model-View-ViewModel
- Model memorizza i dati
- View mostra i dati e ascoltare le azioni dell'utente
- ViewModel gestisce, salva e elabora i dati e stabilisce la comunicazione tra view e model

Vue si concentra sul livello ViewModel