
Fino ad adesso abbiamo costruito una pagina che contiene esclusivamente la struttura e il contenuto in HTML.
Adesso vediamo come integrare gli stili

# Che cosa sono i CSS
I CSS sono un insieme di regole di stile che permettono di definire come sono visualizzati gli elementi HTML.

# Le basi
Non vogliamo più visualizzare le pagine in stile "*necrologio sul giornale*" 
Una regola CSS è composta da due parti fondamentali:
- Un selettore, per identificare un insieme di elementi HTML
- Le regole

### Includere i CSS
- Si può utilizzare il tag `<link>` nella sezione `<head>` per utilizzare file esterni
```html
<link rel="stylesheet" type="text/css" href="mystyle.css" media="screen">
```
- Si può utilizzare il tag `<style>` per specificarli all'interno del file HTML
- L'attributo `media` permette di specificare una tipologia di dispositivo a cui applicare il foglio di stile:
	- `all` (default)
	- `screen` (per i normali browser web)
	- `print` (per la stampa)
	- `aural` (browser vocali)

# Sintassi

```css
h1 /* selettore */ { 
	/* dichiarazione */
	color: blue;
	font-size: 12px;
}
/*regola*/
```
## Selettori
Vengono utilizzati per selzionare un insieme di elementi dell'albero del documento
Ne esistono di diverse categorie:
- Universali
- Tipi (tag)
- Classi
- Id

Alcuni sono basati su relaziozioni dell'albero HTML:
- Figli
- Discendenti

Altri sono basati su condizioni specifiche:
- Valiri di attributi
- Pseudo-classi

### Selettore universale
```css
* { color: blue; }
```
`*` è il selettore universale
- Possono essere combinati con delle condizioni

### Selettore per tipo (tag)
```css
h2 {color: blue;}
```

Sono specificati utilizzando il nome del tag a cui applicare la regola

### Selettore per ID
Seleziona l'elemento unico con attributo `id` uguale al valore
```css
#mimmo {color : red;}
```
Dove `mimmo` (senza il cancelletto) è il tag a cui applicare la regola
### Selettore per Classi
Seleziona tutti gli elementi appartenenti a una `class`
```css
.clA {color: blue;}
```
Dove `clA` (senza il punto) è la class a cui applicare la regola
- Un elemento può appartenere a più classi (separate da uno spazio)

### Selettori combinati tipo-id o tipo-class
Seleziona tutti gli elementi di tipo x con id y
```css
h2#fun {color: red;}
```

Seleziona tutti gli elementi di tipo x con classe y
```css
h2.fun {color: red;}
```

### Selettori per relaziozioni
Permette di selezionare elementi di un certo tipo, discendenti da un altro
```css
h1 em {color: red;}
/*Tutti gli elementi em che discendono da un h1*/
```

```css
h1 > em {color: red;}
/*Tutti gli elementi em FIGLI di un h1*/
```

Si possono realizzare catene di discendente

### Selettori su attributi
Si possono effettuare selzioni in base ai valori di un attributo.
Si possono utilizzare diversi operatori come:
- `=` valore attributo esattamente uguale a quello specificato
- `=~` valore contenuto nella lista di valori
```css
a[rel="copyright"] {
	color: red;
}
```

### Selettori per pseudo-classi
Sono utilizzati per selezionare elementi con informazioni che sono esterni alla definizione del documento
I più importanti sono:
- `a:link` applicabile ai link non visitati
- `a:visited` definisce gli stili per i link visitati
- `img:hover` definisce gli stili per un elemento quando il mouse ci passa sopra
- `button:active` definisce gli stili per un elemento quando viene attivato
- `input:focus` definisce gli stili per un elemento di input quando viene selezionato

> "*io vi posso insegnare come tagliare una salsiccia col coltello, però voi potete anche sgozzarci una persona poi*"~ G. Cherchi

### Raggruppare più selettori

### Specificità dei selettori
In generale non si dovrebberp definire regole contrastanti per lo stesso elemento HTML
- Con la regola `!important` si sovrascrive la specificità: peggio del `goto`
- Gli stili inseriti con `<style>` ha priorità maggiore rispettp alle regole del file esterno
- In caso di specificità pari si usa l'ordine in cui sono scritte nel file `.css` (prima l'ultima regola)

