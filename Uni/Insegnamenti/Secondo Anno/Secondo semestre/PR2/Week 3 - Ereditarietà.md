#Uni/Insegnamenti/Secondo_Anno/PR2 
```java
public class Rettangolo {	
	private double x,y; //posizione in alto a sx
	private double larghezza; // dimenzione orizzontale
	private double altezza; // dimensione verticale

	/** Crea un rettangolo alla posizione specificata */	
	public Rettangolo(double x, double y, double larghezza, double altezza) {
		this.x = x;
		this.y = y;
		this.larghezza = larghezza;
		this.altezza = altezza;
	}
	
	public double area() {
		return larghezza * altezza;
	}

	/** Raddoppia il rettangolo facendo coincidere il nuovo centro
	* con (x,y) iniziale */
	public void raddoppia() { // notare il void
		x -= larghezza;
		y -= altezza;
		larghezza *= 2;
		altezza *= 2;
	}
}
```

# Riuso tramite inclusione
Data la classe `Rettangolo` che abbiamo definito prima, definire `Quadrato` richiede di utilizzare molte proprietà e moduli uguali a Rettangolo.
Possiamo quindi includere un Rettangolo nella nostra implementazione di Quadrato per riutilizzare la classe già definita.

```java
public class Quadrato {
	private Rettangolo rettangolo; // rappresenta questo quadrato
	
	/** Crea un rettangolo alla posizione specificata */
	public Quadrato(double x, double y, double lato) {
		// notare l'inizializzazione del rettangolo
		this.rettangolo = new Rettangolo(x, y, lato, lato);
	}
	
	public double area() {
		return rettangolo.area();
	}
	
	/** Raddoppia il quadrato facendo coincidere il nuovo centro
	* con (x,y) iniziale */
	public void raddoppia() { // notare il void
		rettangolo.raddoppia();
	}
}
```

# Ereditarietà
Un altra tecnica fondamentale di riuso/riutilizzo è quella dell'**ereditarietà**.
Il meccanismo dell'ereditarietà è fondamentale nei linguaggi di programmazione orientata agli oggetti: serve a rappresentare gerarchie (alberi) di classi/oggetti senza dover ripetere il codice già scritto per classi più generali.

> L'ereditarietà si può utilizzare quando tra le due classi si ha una relazione di tipo *is-a*

Per far si che una classe `A` erediti da una classe `B` utilizziamo la sintassi
```java
public class A extends B {...}
```
Si dirà allora che `A` è una *sottoclasse* di `B`, mentre `B` è una *superclasse* di `A`

Possiamo anche ereditare in maniera più complessa
```java
public class A extends B {...}
---
public class B extends C {...}
```
`A` è sottoclasse di `B` e di `C`

Vengono ereditati tutti i metodi e attributi, con eccezioni
- i **costruttori** non sono ereditati
- non si ha la visibilità di metodi o attributi `private`: sono classi diverse. Questi metodi non vanno però ridefiniti, perché sono comunque esistenti

```java
public class Quadrato extends Rettangolo {
	public Quadrato(double x, double y, double lato) {
		// super() si usa per richiamare il costruttore della superclasse
		super(x, y, lato, lato);
	}
}
```
La keyword `super()` richiama il costruttore della superclasse diretta.
- Se non chiamiamo esplicitamente `super()`, automaticamente viene richiamato `super()` (costruttore senza parametri)
# Costruttori, metodi ed ereditarietà
La chiamata di tutti i metodi e dei costruttori è basata sul nome del metodo e dalla sua firma, deve essere perciò unica.

Quando non si definiscono costruttori, viene automaticamente definito un costruttore di default, senza parametri, con il suo corpo vuoto: quando si richiama un costruttore la prima cosa che viene fatta è richiamare il costruttore della sua superclasse.
Ove non specificato, le classi estendono una classe speciale detta `Object` (l'unica a non avere superclassi).
# Cast
L'operazione di cast serve a "forzare" il tipo di un oggetto. Infatti a runtime ed a compile-time i tipi possono essere diversi.
- **upcast** (da sottoclasse a superclasse): viene fatto automaticamente
- **downcast** (da superclasse a sottoclasse): l'operazione non sempre è corretta, è quindi il programmatore a dover esplicitare quando ciò sia effettivamente possibile
# Override
L'override di un metodo è l'operazione con cui si "sovrascrive" un metodo in una sottoclasse, mantenendo la firma della superclasse
```java
public class Quadrato extends Rettangolo {
	public Quadrato(double x, double y, double lato) {
		// super si usa per richiamare il costruttore della superclasse
		super(x, y, lato, lato);
	}
	
	// Sovrascriviamo il metodo toString ereditato dalla superclasse Object
	@Override
	public String toString() {
		return "Quadrato in posizione (" + x + "," + y + ") e di lato " + lato;
	}
}
```
Attenzione, `x`  e `y`, sono dichiarati privati in `Rettangolo` e quindi non accessibili da `Quadrato`

# Package
Diverse classi che fanno parte di uno stesso progetto, in Java, possono essere raggruppate in gruppi funzionali, detti `package`. Sulla macchinacorrispondono a una directory
I nomi dei package sono *generalmente* degli URL invertiti, seguiti dal nome della classe.
Ad esempio il nome completo di `Object` è `java.lang.Object`
Si dichiarano all'inizio del file con `package <nomePackage>`
Sono utilizzati per evitare clash tra namespace delle classi
# Modificatori di accesso

| **Modifiers**       | Class | Package | Subclass | World |                              |
| ------------------- | ----- | ------- | -------- | ----- | ---------------------------- |
| `public`            | Y     | Y       | Y        | Y     | Tutte le classi              |
| `protected`         | Y     | Y       | Y        | N     | Stesso package o sottoclassi |
| Nessun modificatore | Y     | Y       | N        | N     | Stesso package               |
| `private`           | Y     | N       | N        | N     | Stessa classe                |
Nessun modificatore è il modificatore di default, noto anche come `package-private`

# Array
```java
int[] array = new int[3];
int[] array = new int[]{1,2,3};
int[] array = {1,2,3};
```
Gli array in Java possono essere creati in tre modi diversi:
1. Creiamo un array di int n int, inizializzato a 0
2. Creiamo un array di int e lo inizializziamo ai valori che vogliamo
3. È possibile creare un array e inizializzarlo ai valori desiderati **solo** allo stesso tempo dell'inizializzazione della variabile con questa forma ridotta

Gli array funzionano allo stesso modo per i tipi primitivi e per gli oggetti
```java
String[] stringArray = new String[3]; // 3 è il numero di stringhe, non di chars
String[] stringArray = new String[]{"a", "b", "c"};
String[] stringArray = {"a", "b", "c"};
```

L'inizializzazione di default degli array di oggetti è `null` anziché 0

```java
Object o = new Quadrato(0,0,10);
Object[] arr = new Object[10];
arr[0] = new Object();
arr[1] = new Quadrato(0,0,20);
arr[2] = o;
```
Poiché tutti gli oggetti ereditano da `Object`, possiamo avere array con oggetti appartenenti a classi diverse, ma tutte sottoclassi della classe dell'array

```java
Rettangolo[] rettangoli = new Rettangolo[10];

rettangoli[0] = new Rettangolo(0,0,10,20);
rettangoli[1] = new Quadrato(0,0,10);
rettangoli[2] = (Quadrato) o;
```

`rettangoli.lenght` è un attributo che indica la dimensione dell'array

```java
int n = 0;

for (int i = 0; i < rettangoli.length; i++) {
	if (rettangoli[i] != null) {
		n++;
	}
}
```
Questo codice invece salva in `n` il valore di posizioni inizializzate dell'array

# Lab
## Ereditarietà
Abbiamo visto come oggetti e classi hanno attributi e metodi. 
Per esempio data una classe Studente con attributi `nome`, `cognome`, `eta` e `matricola` e una classe Docente con attributi `nome`, `cognome`, `eta` e `insegnamento`.
Possiamo riconfigurare queste classi organizzando gli attributi `nome`, `cognome` e `eta` nella classe Persona e rendendo le classi Studente e Docente sottoclassi di Persona, ereditando attributi e metodi comuni

```java
public class Studente extends Persona {
	private int matricola; // Come attributi definiamo solamente quelli da aggiungere a Persona
	
	public Studente(String nome, Strinf cognome, int eta, int matricola) {
		super(nome, cognome, eta); // Richiamiamo con super() il costruttore di Persona
		this.matricola = matricola;
	}
...
```
Il costruttore `super()` di Persona deve sempre essere la prima chiamata all'interno del costruttore della sottoclasse. Quando il costruttore della superclasse non prende parametri non è necessario esplicitarlo e automaticamente il compilatore aggiunge il costruttore vuoto.

Se gli attributi di Persona sono `private` non ci posso accedere direttamente dalla sottoclasse Studente, dobbiamo quindi utilizzare i metodi getter e setter di Persona che possiamo richiamare con la keyoword `super`.
```java
...
	public String getNome() {
		return super.getNome();
	}
```
## Override dei metodi
Abbiamo le due sottoclassi e la superclasse, diciamo override dei metodi, quando dato un metodo della superclasse generico, lo vogliamo specializzare per ciascuna sottoclasse

## Casting
Si dice **upcasting** l'operazione di salvare in una variabile di tipo della superclasse un oggetto della superclasse
Ad esempio
```java
Persona p = new Docente();
```

È detta **downcast** l'operazione inversa, ovvero salvare in una sottoclasse un oggetto che era salvato in una variabile della superclasse, di nuovo in una variabile della sottoclass.
Per fare ciò è necessario esplicitare il cast come in C
```java
Docente d = (Docente)p;
```

Per assicurarsi che il cast sia fattibile si può utilizzare l'operatore `isistanceof` che ci indica se l'oggetto può essere convertito in un riferimento di quel tipo
Ad esempio
```java
if (p instanceof Docente){
	Docente d = (Docente) p;
}
```

> Attenzione: Java determina il metodo da invocare mediante la ricerca dinamica del metodo.
 Il metodo da invocare è sempre deciso in base al tipo reale dell’oggetto a runtime.