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