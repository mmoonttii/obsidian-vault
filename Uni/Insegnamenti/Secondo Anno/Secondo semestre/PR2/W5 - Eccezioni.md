#Uni/Insegnamenti/Secondo_Anno/PR2 
# Vantaggi delle eccezioni
1. Separazione del codice che gestisce l'errore dal codice che implementa le funzionalità del software
2. Propagazione dell'errore: l'errore può venire gestito in un posto diverso da dove è stato generato
3. Raggruppamento degli errori in base al tipo

# Cos'è un'eccezione
Una eccezione è un evento che occorre **durante l'esecuzione di un programma**, interrompendo il normale flusso di istruzioni.

Quando un errore occorre dentro un metodo, tale metodo crea un oggetto (l'eccezione) che viene rilasciato al runtime (l'interprete). Tale oggetto contiene le informazioni sull'errore, il tipo ed altre informazioni. Quando avviene questo si dice che **è stata lanciata una eccezione**.

Una volta che l'eccezione è lanciata, il sistema cerca se esiste del codice che possa gestirla. La ricerca viene fatta seguendo la call stack (la pila delle chiamate ai metodi)

## Lanciare e catturare un'eccezione
Per lanciare una eccezione si utilizza il comando throw:
```java
throw oggettoEccezioneDaLanciare;
```

L'eccezione è un oggetto e appartiene a una classe ed è quindi necessario prima di tutto costruire l'oggetto. Esistono diverse tipologie di classi per eccezioni

```java
IOException eccezione = new IOException("file illeggibile");
throw eccezione
```

È possibile anche comprimere in una sola linea
```java
throw new IOException("file illeggibile");
```

Una volta che si verifica l'eccezione il runtime prova a cercare un **exception handler** (gestore dell'eccezione) adatto a gestire l'eccezione lanciata.
Se viene trovato, l'handler si dice che cattura l'eccezione, gestendola ed interrompendo la ricerca e la propagazione dell'eccezione.

## Gerarchie delle classi di eccezioni
In Java esistono tre tipi di oggetti lanciabili
- Errori: `Error` e sottoclassi
- Eccezioni a runtime: `RuntimeException` e sottoclassi
- Eccezioni checked: tutte le altre

### Checked exceptions
Le eccezioni checked sono tutti i throwable, tranne `Error` e sottoclassi e `RuntimeException` e sottoclassi.
Rappresentano condizioni eccezionali che dovrebbero essere previste e gestite da un'applicazione ben scritta

### Runtime Exceptions
Le `RuntimeException` rappresentano condizioni eccezionali che di solito non sono previste o gestite: indicano solitamente bug di programmazione come errori logici o di uso improprio delle API

### Errors
Gli `Error`, non sono considerati un'eccezione, nonostante siano lanciabili, e rappresentano condizioni eccezionali esterni all'applicazione non prevedibili o gestibili, come memoria esaurita o rottura di hardware

# Gestire checked exceptions
Per compilare, il codice Java deve rispettare il **Catch or Specify Requirement**, un vincolo imposto dal compilatore per cui tutte le eccezioni checked devono:
- Essere racchiuse da un blocco `try` / `catch` che catturi e gestisca l'eccezione
- Il metodo dichiara che può lanciare tale eccezione nella sua firma

## Blocco `try` / `catch` / `finally`
Con questo blocco possiamo gestire tutte le eccezioni
```java
try {
	// codice che può potenzialmente
	// lanciare eccezioni
} catch (ExceptionTypeA name) {
	// codice che gestisce eccezioni
	// di tipo ExceptionTypeA
} catch (ExceptionTypeB name) {
	// codice che gestisce eccezioni
	// di tipo ExceptionTypeB
} [...]
} finally {

}
```
I catch vengono esplorati sequenzialmente, fermandosi al primo il cui tipo corrisponde all'eccezione lanciata (l'ordine quindi è importante)
Utilizzare costrutti del genere rende il codice più leggibile e manutenibile
## Specificare `throws` nel metodo
Quando non si vuole catturare una determinata eccezione in un metodo è necessario specificare che questo metodo potrebbe lanciarla, senza catturarla: facendo così chi utilizza il metodo potrà gestirla come preferisce.
Per specificare che il metodo lancia eccezioni che non sono catturate si utilizza `throws <classe eccezione>`

## Leggere un file di testo
Quando leggiamo un file di testo, è necessario, attraverso un blocco `try` / `catch` / `finally`, assicurarsi che il file sia disponibile e leggibile e che la chiusura del file avvenga correttamente e in ogni caso.

```java
public static void main(String[] args) throws java.io.IOException {
	BufferedReader br = new BufferedReader(new FileReader("file.txt"));
	StringBuilder sb = new StringBuilder();
	try {
		String line = br.readLine();
		while (line != null) {
			sb.append(line);
			sb.append(System.lineSeparator());
			line = br.readLine();
		}
		String everything = sb.toString();
	} finally {
		br.close();
	}
	System.out.println(sb);
}
```

`BufferedReader` è la classe di libreria degli oggetti che rappresentano la lettura in maniera bufferizzata (ad esempio linea per linea). È necessario associare a `BufferedReader` un reader al momento della costruzione, in particolare noi possiamo aprire un file utilizzando la classe `FileReader`
### try-wiyh-resources
Il try-with-resources è un try che dichiara una o più risorse. Una risorsa è un oggetto che deve essere "chiuso" una volta che sia finito (es. i file, specialmente in scrittura). Questo costrutto assicura che la risorsa sia chiusa al termine del try.

Per fare ciò è necessario che gli oggetti usati come risorsa devono implementare `java.lang.AutoCloseable`.

Si identifica per la presenza delle parentesi tonde, dentro le quali si creano le risorse che andranno chiuse. In caso di più risorse, si separano con il punto e virgola (;).

```java
static String readFirstLineFromFile(String path) throws IOException {
	// try/finally (può lanciare eccezione nel close)
	BufferedReader br = new BufferedReader(new FileReader(path));
	try {
		return br.readLine();
	} finally {
		if (br != null) br.close();
	}
	
	// try-with-resources (lancia solo eccezione dentro il try)
	try (BufferedReader br = new BufferedReader(new FileReader(path))) {
		return br.readLine();
	}
}
```

# Lab
## Il metodo `equals()` e il suo override
- Abbiamo già visto il metodo `toString()` e il suo override
Il metodo `equals()` permette di fare il confronto diretto tra due oggetti **appartenenti alla stessa classe**: ad esempio per una classe Persona possiamo andare a confrontare nome, cognome ed età.

> Prima di fare l'override l' `equals()` della classe Object confronta l'indirizzo di memoria

`equals()` deve rispettare le proprietà di
- **riflessività**: `x.equals(x)`
- **simmetria**: `x.equals(y) => y.equals(x)`
- **transitività**: `x.equals(y) && y.equals(z) => x.equals(z))`
- `x.equals(null) == false`

```java
@Override
public boolean equals(Object obj){
	if (this == obj) {
		return true
	} else if () {
	} else if () {
	}
	
	Persona altraPersona = (Persona) obj;
	
}
```

### Override del metodo della superclasse

## Variabili di classe `static`
`static` è una keyword per metodi e variabili che ci permette di distaccarci dal concetto di istanza di un oggetto e definire variabili che 

### Metodi `static`
I metodi di classe, o static, sono metodi che non si riferiscono all'istanza di un oggetto in particolare, ma alla classe in generale

## Eccezioni
Gli errori non sono bug (errori di semantica), ma la gestione delle diverse possibilità che possono accadere
### Errori checked
Sono controllati a tempo di compilazione ed è necessario gestirli per compilare con successo.
>  Generalmente sono errori dovuti a IO: file, stream
### Errori unchecked
Non siamo obbligati a gestirli, nonostante sia buona norma
### `throws`
Con la clausola `throws` il metodo specifica che può lanciare un'eccezione e stiamo demandando al chiamante il compito di gestire l'eccezione
### Gestire l'eccezione
Catturiamo e gestiamo l'eccezione con un `try-catch`.
Quando viene lanciata un'eccezione, tutte le righe successive non sono eseguite e il runtime salta direttamente al catch che gestisce l'estensione.

I catch lavorano in cascata: ad esempio se abbiamo un catch di un errore molto generico all'inizio, tutti gli errori verranno catturati dalla classe più ampia. È quindi necessario dichiarare i catch dall'errore più particolare a quello più generale.

### `finally`
Il blocco `finally` viene sempre eseguito dopo un try-catch, sia quando l'esecuzione va a buon fine, che in caso contrario, permettendo 

### Altre eccezione
Poichè le eccezioni sono calssi, possiamo anche noi definire delle nuove eccezioni

