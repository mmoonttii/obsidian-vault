#Uni/Insegnamenti/Secondo_Anno/FPW 
# Caratteristiche
JavaScript è:
 - Un lingugaggio ad alto livello
 - Interpretato
 - Multi-pardigma (imperativo, ad oggetti e funzionale)

JavaScript permette di rendere dinamiche le pagine, modificando le pagine a seconda delle necessità
Nasce come tecnologia lato client, ma grazie a nodeJS può essere utilizzato anche nel backend

Il codice JS si può aggiungere direttamente in una pagina HTML con il tag `<script>`

## Commenti

## Separare le istruzioni
Non è strettamente necessario separare le istruzioni con il punto e virgola, ma è fortemente consigliato in quanto alle volte il semplice newline non è sufficiente

## Variabili
Si dichiarano con `let`, le costanti con `const`
I nomi possono iniziare solo con a-zA-Z$_

## Dinamicamente tipato
Il tipo di una variabile può cambiare

## Tipi
- `number`: sia per interi che per float
- `bigint`
- `string`
- Non abbiamo un tipo character
- `boolean`
- `null`
- `undefined`
- `object`

### Tipo number
Infinito
NaN
_
Classe Math
### Stringhe
Possono essere racchiuse tra `" "`, `' '`
In particolare usando i backtick \` possiamo utilizzare stringhe con "funzionalità estese"
Esistono attributi e funzioni di libreria per effettuare controlli sulle stringhe
Usiamo le quadre `[n]` per estrarre l' $n$ -esimo carattere
Non è possibile modificare un singolo carattere, ma solo l'intera stringa

### Cast impliciti

## Operatori
+ + Addizioni o concatenazione di stringa
+ -
+ *
+ /
+ **
+ =
+ ++/--
+ +=. -=, \*=, \/=
+ <, >, >=, <=, \=\=, !=\=
+ \=\=\=, !\=\=: **operatore di uguaglianza stretta**: controlla sia valore che tipo
```js
let a = "445"
let b = 445
b == a
b === a
```

## If
`if (<cond>) {<se_vera>} else {<se_falsa>}`
`let result = (<cond>) ? <se_vera> : <se_falsa>`
## Switch
Accetta espressioni arbitrarie sia nello switch che nei caratteristiche

## Loop
While
Do..while
For (;;)
Etichette: per uscire direttamente da molti cicli annidati

## Funzioni
```js
function <nome_fun> (par, ...) {
}
```
Una funzione dichiarata in un determinato scope, funzionano solo in quello scope
I parametri, quando non sono oggetti, sono passati per valore

Se non si passa un parametro, non ci sono problemi, viene assunto come undefined
Possiamo però impostare valori di default

Return senza niente ritorna undefinde

## Variabili locali e globali

## Function expression
La funzione è dichiarata come una funzione e assegnata a una variabile
## Arrow function
## Callback
## setTimeout e setInterval

## Oggetti
### Creazione
Sintassi costruttor
Sintassi letterale

### Proprietà

### Garbage collection

### Metodi
### this
### Costruttore e operatore new
### Classi
### Conversione da oggetti a tipi primitvi
### Array
### Maatrici
### Date e time
### JSON

## Try catvh
### Throws
## Metodi
