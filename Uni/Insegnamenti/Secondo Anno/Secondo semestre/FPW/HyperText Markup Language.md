#Uni/Insegnamenti/Secondo_Anno/FPW
Inizialmente andremo a creare un'applicazione web statica, utilizzando le tecnologie HTML e CSS.
Con il codice HTML andiamo a definire **solo e soltanto** la struttura della nostra pagina web.

**HTML NON è un linguaggio di programmazione**, è un linguaggio di markup perché non permette di utilizzare i costrutti tipici dei linguaggi di programmazione.
# Tag
Le parole chiave dell'HTML sono chiamate **tag** e sono contenute tra `< >`. Sono di solito accoppiati, un tag di apertura e un tag di chiusura. Alcuni tag sono **self-closing**

Tag e elemento sono termini spesso utilizzati erroneamente come sinonimi, ma l'elemento è tutto ciò che è compreso tra tag di apertura e chiusura, tag compresi.
```html
<h1>Titolo</h1>
```
### Attributi
I tag possono avere degli attributi, per fornire informazioni addizionali su un elemento. Sono sempre specificati sul tag di apertura, e sono formati da coppie nome-valore
```html
<a href="http://example.com">Esempio link</a>
```

Alcuni esempi di attributi sono
- `class` per definire delle classi a cui appartengono più tag (usato nel CSS)
- `id` id per l'elemento
- `name` nome non univoco per l'elemento
- `style` stile CSS per l'elemento specificato come attributo
- `title` informazioni supplementari su un elemento
# Struttura di una pagina HTML

```html
<!DOCTYPE html>
<html>
	<head>
		...
	</head>
	<body>
		...
	</body>
</html>
```

- `<!DOCTYPE html>` indica al browser la versione di html in uso ed è necessario per la corretta interpretazione dei tag
- `<head>` contiene informazioni, che non vengono visualizzate nel corpo della pagina, necessarie per il browser, etc
- `<body>` contiene le parti che verranno visualizzate sulla pagina

La struttura di una pagina web è una struttura ad albero ed è molto utile per diverse funzionalità, come applicare stili, per attribuire comportamenti con javascript
### Commenti
```html
<!-- FINALMENTE IL COMMENTO -->
```
## Head
Il tag head contiene informazioni generali sulla pagina, come:
- `<title>`: il **titolo** quello visualizzato nel tab del browser, o nel motore di ricerca
- Il set di caratteri utilizzati
- `<link ...>`: indica dove andare a prendere script esterni o fogli di stile css, è usato anche per settare la favicon
- `<base href="...">`: permette di ridefinire l'URL di base per i collegamenti relativi nella pagina
- `<style>`: permette di definire regole CSS nel documento
- `<meta>`: contiene informazioni particolari sulla pagina web, interessanti al motore di ricerca o necessari al browser
## Body
### Caratteri speciali
Bisogna prestare attenzione ai caratteri accentati, in quanto browser diversi possono utilizzare charset diversi. Per risolvere questo problema si possono utilizzare due metodi:
- Esplicitare il charset con un tag meta `<meta charset="utf-8">`
- Utilizzare le **html entries**, codici speciali per indicare simboli non ASCII come à - `&agrave`
### Titoli
Definiscono i titoli nella struttura dei documenti.
Esistono di 6 dimensioni da `<h1>` a `<h6>`, dove `<h1>` è il più grande, ed è buona norma che si abbia solamente un tag `<h1>`
Attenzione l'utilizzo degli heading, è legato solamente alla struttura, non alla dimensione o stile del testo che sono impostati con stili CSS
Non sono da utilizzare per fare un testo più grande, in quanto sono utilizzati dai motori di ricerca per riconoscere la struttura del documento
### Paragrafi
Un paragrafo è definito dal tag `<p>`
- I browser automaticamente aggiungono uno spazio prima e dopo ogni tag
- Gli spazi all'interno di un tag paragrafo sono ignorati dai browser
- Per forzare l'andata a capo si utilizza il tag `<br>`
- Per disegnare una linea orizzontale si usa il tag `<hr>`
### Formatting tags
Sono i tag per formattare il testo
- Bold: `<strong>` o `<b>`. I due tag si differenziano dal fatto che `<strong>` è un tag semantico e indica un testo più importante per i motori di ricerca
- Italic: `<em>` (semantico) o `<i>`
- Codice: `<code>`
- Pedice `<sub>` e Apice `<sup>` 
- E molti altri
### Link
I link si creano con il tag `<a>`, quello compreso tra i tag di apertura e chiusura rappresenta ciò che sarà cliccabile e mostrato sulla pagina.
Attributi del tag:
- Con l'attributo `href` si indica il collegamento da aprire
- L'attributo `target="_blank"` apre il documento in una nuova finestra

È possibile definire un **segnalibro**, marcando una parte del documento con un tag `<a>` e l'attributo `<id>`. Per effettuare il collegamento si definisce un altro tag `<a>` inserendo nell'attributo `href` l'id che si vuole raggiungere preceduto dal `#`.
### Immagini
Sono definite dal tag self-closing `<img>`
Gli attributi sono
- `src` che indica l'immagine che vogliamo prendere
- `title`
- `alt`: rappresenta del testo alternativo da visualizzare quando non è disponibile la risorsa, necessario anche per i non vedenti
- `width`
- `height`
### Tabelle
Definite dal tag `<table>`, `<th>` che apre e chiude le intestazioni, `<tr>` indica le righe, `<td>` definisce le diverse celle 

```html
<table>
<tr>
	<th> Header 1 </th>
	<th> Header 2 </th>
</tr>
<tr>
	<td> Cella 1 </td>
	<td> Cella 2 </td>
</tr>
<tr>
	<td> Cella 3 </td>
	<td> Cella 4 </td>
</tr>
</table>
```
### Liste
Le liste sono aperte dal tag
- `<ol>` per le liste ordinate
- `<ul>` per le liste non ordinate

All'interno della lista gli elementi si denotano con il tag `<li>`
# Form
Contiene elementi che consentono l'input da parte dell'utente
## Input
Possono essere di diversi tipi, numerici, testuali, di scelta.
Utilzziamo il tag `<input>` differenziando con l'attrobuto `<input>`, o tag come `<select>` e `<textarea>`
L'input fornito diventa una coppia chiave-valore che verrà utilizzata lato server
È possibile specificare una `label` per specificare un'etichetta testuale nell'elemento di input
### Input testuale
```html
<input type="text"> per testi brevi/Valori
<textarea> per testi lunghi
<input type="password"> per non visualizzare quello che si inserisce
```

Con l'html 5 si sono introdotti molte tipologie di tag

```html
<form ...>
	<label for="id_short">Testo breve</label>
	<input... />
	<br>
	
	<label for="id_psw">Password</label>
	<input type="password" />
	<br>
	
	<label for="id_long">Testo lungo</label>
	<textarea>
		Un testo molto lungo
	</textarea>	
```
### Valori di input con HTML 5
- Color
- Date
- Email
- File
- Number
- ...
## Pulsanti
Si possono inserire utilizzando due tag `<input>` o `<button>`

Entrambi ammettono i valori per `type`:
- `submit` per inviare il form al server
- `button` per un bottone generico da personalizzare con JS
- `reset` cancella gli input dell'utente dai campi del form

I due tag possibili si differenziano dal fatto che `<input>` ammette testo solo nell'attributo `value` o un'immagine con l'attributo `image` e non ammette figli, mentre `<button>` ammette figli

### Esempi
```html
<input type="submit" value="Submit con tag input" />
```
## Selezione a scelta singola
Diversi tipi di controllo a seconda del numero di scelte ammissibili
- Bassa cardinalità ($7 \pm 2$): radio button `<input type="radio">`
- Media cardinalità ($10 : 20$): drop down list `<select>`
- Alta cardinalità (più di 20): list box `<select size="n">`

Queste diverse tipologie di scelta non sono regole fisse, ma aiutano l'utente nell'interazione con la pagina
### Esempio
```html

```
## Selezione a scelta multipla
Diversi tipi di controllo a seconda del numero di scelte disponibili
- Cardinalità medio-bassa (fino a 15): check-box `<input type="checkbox">`
- Cardinalità medio-alta (più di 15): list box `<select multiple>`
Per una cardinalità alta è meglio utilizzare altri metodi.
### Esempio
```html

```
# Sezioni
Le sezioni all'interno dei documenti HTML sono utilizzate per:
- Separare i contenuti della pagina
- Permettere di definire layout

- `<div>`: definisce un blocco del documento separato dagli altri
- `<span>`: definisce una sezione inline (non separata dalle altre)
## Sezioni semantiche in HTML 5
Con l'HTML 5 si sono introdotti dei tag semantici, che suddividono la pagina in sezioni, ma introducendo anche un significato ad ogni sezione.
Ognuno di questi è visualmente indistinguibile da un tag `<div>` qualunque, ma aiutano il browser a comprendere il tipo di contenuto e il programmatore a identificare il loro utlizzo

- `<header>`
- `<nav>`
- `<article>`
- `<section>`
- `<footer>`
- `<aside>`
# Search Engine Optimization - SEO
Le SEO sono una serie di tecniche che consentono alla nostra app web di esser nei primi posti tra i risultati di un motore di ricerca.
### I motori di ricerca
I motori di ricerca funzionano su tre step:
- **scansione** (crawling): programmi automatici scansionano continuamente le pagine sul web, seguendo i link presenti alla ricerca di nuovi contenuti
- **indicizzazione** (indexing): viene creata un'indicizzazione dei contenuti nelle pagine web
- **posizionamento** (ranking): quando l'utente effettua una query, questa viene utilizzata per creare una classifica delle pagine sui server in ordine di pertinenza
### SEO e HTML
Alcuni accorgimenti possono essere presi a livello delle pagine HTML:
- Inserire sempre il tag `<title>` per attribuire un titolo univoco, breve e significativo ad ogni pagina del sito
- Inserire sempre una descrizione informativa e interessante che sia completa con il tag `<meta name="description" ...>`
- Inserire sempre delle keyword pertinenti alla nostra app web `<meta name="keyword" ...>`
- Scrivere codice HTML valido e standard
- Non creare troppe ramificazioni (tramite link) nella struttura del sito.
- Evitare link che portano a pagine inesistenti (error 404)
- Utilizzare il tag `<img>` con l'attributo `alt` con una descrizione breve e significativa e un nome breve e descrittivo per il tag `src`
- Utilizzare adeguatamente i tag di heading, in particolare non utilizzare più di un tag `<h1>` nella stessa pagina
- Non abusare del tag `<strong>` nella stessa pagina (si perde il concetto di importanza se tutto è importante)
- Creare URL significativi e breci
- Etc etc etc