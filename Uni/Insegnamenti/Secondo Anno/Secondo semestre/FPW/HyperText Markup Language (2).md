#Uni/Insegnamenti/Secondo_Anno/FPW 
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
