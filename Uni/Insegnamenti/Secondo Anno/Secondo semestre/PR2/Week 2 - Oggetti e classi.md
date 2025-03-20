#Uni/Insegnamenti/Secondo_Anno/PR2 
# Elementi di base in Java
### Tipi

>  Un **tipo** definisce l'insieme di valori e le operazioni associate a tali valori

In Java sono presenti 8 **tipi primitivi**
I tipi primitivi non sono strettamente necessari in un linguaggio ad oggetti, si potrebbe vivere solamente utilizzando le classi. I tipi primitivi **NON** sono classi e i loro valori, non sono quindi oggetti di una classe
- `boolean`
- `char`: che rappresenta caratteri Unicode 16-bit (se vogliamo scrivere il nome di un mobile ikea non ci bastano i 256 caratteri della tabella ASCII)
- Tipi aritmetici:
	-  interi:  `byte, short, int, long` -- **con segno**
	- a virgola mobile: `float, double`

### Variabili
Servono per immagazzinare valori da utilizzare successivamente.
Hanno un tipo (statico, determinabile a compile-time), nome e un valore

### Identificatoro

### Assegnamento
L'assegnamento è l'operatore che is occupa di assegnare a una variale un valore

Creare una variabile e assegnamento sono due operazioni distinte

# Oggetti e classi
Gli oggetti sono astrazioni tipiche di questa categoria di linguaggi di programmazinoe
> Sono entità che incorporano uno stato e sono manipolabili nei programmi attraverso metodi associati a quell'oggetto

Le classi possono essere viste come i template con le quali generiamo gli oggetti, descrivendo le caratteristiche di tutti gli oggetti che appartengono a quella classe

### Classi e metodi
Le classi dichiarano
- Le **proprietà**, dette attributi degli oggetti di tale classe
- I **metodi** sono le operazioni effettuabili sugli oggetti della classe

Gli oggetti sono manipolabili chiamando i loro metodi e le classi determinano ciò che è possibile far con gli oggetti che descrivono

L'**interfaccia pubblica** specifica ciò che si può fare con gli oggetti di quella classe

### Overloading dei metodi
Lo stesso identificatore in una classe, può essere utilizzato per due metodi diversi, purché abbia in input parametri diversi. Possono avere stesso identificatore, ma **firma** diversa.

### Costruire un oggetto
Data una classe, si utilizza la parola chiave `new` seguita dal **costruttore** per costruire un oggetto della classe. Il costruttore è simile ai metodi, ma ha la funzione speciale di creare ed inizializzare un nuovo oggetto, utilizzando dei parametri che gli si possono passare

### Variabili contenenti oggetti
Le variabili associate a tipi non primitivi (quindi oggetti), in realtà contengono un riferimento all'oggetto in memoria (come un puntatore in C)

Gli oggetti rimarranno in memoria fintantoché il **Garbage Collector** (alligatore) del runtime Java, decide di liberare la memoria: Java è un linguaggio memory-managed, dove la gestione della memoria è effettuata automaticamente.

### Esempio di classe: `String`
String genera oggetti inimitabili

### La parola chiave `this`
La parola chiave `this` serve a rappresentare un riferimento all'oggetto su cui è stato invocato il metodo, all'interno della classe di quell'oggetto
```java
class Libro {
	int pagine;
	String titolo;
	int paginaCorrente;
	
	Libro (String titolo, int lunghezza) {
		pagine = lunghezza;
		titolo = titolo; // Questa linea è ambigua, non si riconosce quale è l'attributo e quale è il parametro del costruttore
	}
	
	Libro (String titolo, int lunghezza) {
		pagine = lunghezza;
		this.titolo = titolo; // Utilizzando this risolviamo le ambiguità del costruttore precedente
}
```

### Incapsulamento
Nella OOP possiamo garantire l'incapsulamento, ovvero "proteggere" l'accesso agli attributi della classe, impedendo una modifica dei valori o l'utilizzo di un metodo da parte di chiunque.

Per fare ciò si utilizzano due modificatori di accesso `public` e `private` che specifica che il metodo/attributo/classe può essere acceduto solo all'interno della classe che lo dichiara

### `null` ed eccezioni
Quando si crea una nuova variabile di tipo non primitivo, senza effettuare assegnamenti, la variabile conterrà `null`.

`null` è una parola chiave che
- si può usare ovunque sia necessario un riferimento ad un oggetto
- su una variabile `null` non possiamo chiamare metodi o riferirci ai suoi attributi, altrimenti verrà lanciata una eccezione (un errore a tempo di esecuzione)

```java
...
Libro javabook;
javabook.pagine; // Il programma termina lanciando un'eccezione
...
```

Non tutti gli errori possono essere gestiti staticamente, a compile-time
```java
double value = 10 / randomValue; // È possibile che randomValue sia 0.0
```

### Esempio
```java
public class Rettangolo {
	double altezza
	double base
	double x;
	double y;
	
	public Rettangolo (double x, double y, double base, double altezza)	 {
		this.x = x;
		this.y = y;
		this.altezza = altezza;
		this.base = base;
	}
	
	double area(){
		return this.base * this.altezza;
	}
	
	double perimetro() {
		return 2 * this.base + 2 * this.altezza;
	}
}
```

### Ereditarietà
Pensiamo di voler scrivere la classe Quadrato, molto simile alla classe rettangolo, ma non vogliamo dover riscrivere tutti da zero. 

Questo è come risolvere il problema utilizzando l'inclusione
```java
public class Quadrato {
	private Rettangolo rettangolo;
	
	public Quadrato(double x, double y, double lato) {
		this.rettangolo = new Rettangolo(x, y, lato, lato);
	}
	
	public double area() {
		return rettangolo.area();
	}

}
```

La tecnica dell'ereditarietà è una tecnica di riuso fondamentale dei linguaggi ad oggetti. Serve a rappresentare gerarchia di classi/oggetti, senza dover ripetere il codice già scritto per classi più generali

Ad esempio:
- La classe Persona ha `nome, cognome, età`
- La classe Lavoratore ha `nome, cognome, età, stipendio, dataInizioContratto, datoreDiLavoro`
Notare come il fatto che il lavoratore sia anche una persona causa una ripetizione degli attributi. Questa relazione prende il nome in inglese di **is-a**

# Lab
### Classe ContoCorrente
La programmazione a oggetti si occupa di "***modellare la realtà***" e trasferirla nella programmazione

- La concatenazione di stringa si fa con il `+`
- Per i tipi primitivi possiamo utilizzarli come stringa senza cast esplicit

## Costruttori
Non hanno tipo di ritorno
I loro obiettivo, non è modellare una classe o un metodo, ma costruire un oggetto che poi andremo ad utilizzare
Esistono due tipi principali di costruttori
- Costruttori con parametri: riceve in input valori da assegnare agli attributi dell'oggetto
- Java mette a disposizione un costruttore di default (ereditato dalla classe Object): imposta tutto a null
- Costruttori senza parametri: non riceve alcun parametro in input e quindi associa variabili di default

Poichè in Java, l'identificatore dei metodi è il nome più il numero di parameteri, possiamo creare tanti metodi con lo stesso nome, e diversi parametri. Possiamo quindi creare tanti costruttori per tante situazioni diverse