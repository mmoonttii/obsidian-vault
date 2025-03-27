#Uni/Insegnamenti/Secondo_Anno/FPW 
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

# Proprietà
## Dimensioni
Le dimensioni in CSS possono essere definite utilizzando diverse unità di misura

| Unità | Descrizione |
| ----- | ----------- |
| `%`   |             |
| `in`  |             |
| `cm`  |             |
| `mm`  |             |
| `em`  |             |
| `pt`  |             |
| `px`  |             |
## Colori
Si possono esprimere i colori in tre modi principali:
- Per **nome** per i colori più comuni
- Specificando il valore RGB
	- In esadecimale
	- In valori in base 10
Dall'ultima versione di CSS possiamo definire anche il canale alpha della trasparenza

### Sfondo
`background-color`
[Contrasto](snook.ca/technical/colour_contrast/colour.html)

## Testo
Del testo possiamo cambiare
- il colore
- L'allineamento
- La decorazione
- L'indentazione

### Font
In generale definiamo tre tipologie di font:
- Serif (font con grazie)
- Sans-serif
- Monospace

# Layout della pagina
## Box model
Ogni elemento della pagina è rappresentato, per il browser è un rettangolo (**box**)
Ogni box è composto da 4 rettangoli concentrici
- Content: area del contenuto vero e proprio
- Padding: area libera tra bordo e contenuto
- Border: bordo che racchiude il contenuto
- Margin: area libera tra bordo e altri elementi

### Dimensioni
PEr quanto riguarda il content posso definire:
- `width`
- `height`

Posso controllare poi le proprietà:
- `margin`
- `border`
- `padding`
che posso specificare con `-top` `-bottom`, `left`, `-right`

Altezza totale è quindi data da 
Larghezza totale è quindi data da
### Tipi del bordo
Posso selezionare uno stile del bordo con la proprietà `border-style`
## Tabelle
Possiamo definire:

## Display e visibility
Non è detto che io voglia che tutti gli elementi siano mostrati contemporaneamnete
Utilizzando la proprietà `display`, possiamo regolare questo
- `block`
- `inline`
- `none`
La modalità di default di display dipende dall'elemento
- Blcok: ...
- Inlinen: ...
- Sono sovrascrivibili

Un elemetno può essere nascosto anche con la proprietà `visibility: hidden`. Questa proprietà non mostra l'elemento, ma ne riserva comunque lo spazio necessario.
## Posizionamento
La proprietà `position` regola la posizione di un elemento all'interno della pagina
- Position `static`: ogni elemento è posizionato secondo il flusso normale della pagina
- Position `fixed`: l'elemento è posizionato in modo realtivo alla finestra del browser e rimane in quella posizione anche quando si scorre la pagina
- Position `relative`: consente, con `-top` `-bottom`, `left`, `-right` du modificare la sua posizione  prendendo come riferimento la sua posizione "normale" nel flusso della pagina
- Position `absolute`: con `-top` `-bottom`, `left`, `-right` consente di posizionare l'elemento rispetto alla posizione del oprimo elemento con position diverso da `static`
- Position `sticky`: è un mix tra relative e fixed, in base allo scroll della pagina
### Float
Permette di addossare gli elementi orizzontalmente
È utilizzabile anche per i tag delle liste
LA proprietà `clear` permette di modificare il comportamento di `float`

## Layout patterns
### Layout 2 colonne
Header
Side-bar `<aside>` / Content `<article>`
Footer
## Layout fisso
Definisco in maniera statica la larghezza di una pagina
### Latyout fluido
## Struttura di una pagina desktop
Prendiamo una sturuttura sequenziale dell'html e lo disponiamo utilizzando il css
IL `claae` è una sezione cuscinetto che evita che le side-bar e il conrwntx taglino il footer
Per creare un layout fluido possiamo definire il nostro layout utilizzando le percentuali
# Itnroduzione l responsive design
## Il browser
Oggi le applicazioni web siin visualizzare su dispositivi di tante dimensioni e risoluzinoi,
Abbiamo bisogno, quindil, di adarttare il nostro layout a tanti shcermi
## CSS 2
Con l'attributo `media` prmett di utilizzare un foglio di stule divrso a seconda del dispositivo su cui si disegna la pagina
Media query
`@media screen, handled {}`
## CSS 3
Crea delle media query più potenti in base alla tipologia di dispositivo e sulla dimensione dello schermo.
### Break point
Punti dove il layout della pagina cambiare
## Grid-view
Suddividiamo la pagina in 12 colonne
### Costruire il CSS
```css
* {
	box-sizing: border-box;
}
```
Questo codice serve per includere border, margin e padding nella dimensione del contenuto
Creaiamo poi una classe per ogni colonna
```css
[class*="col-"] {
	float: left;
}
.col-1 { width:8.33%; }
```
Per la riga definiamo il CSS
```css
.row::after {
	content: "";
	clear: both;
	display: table;
}
```
### Media queries e grid-view

