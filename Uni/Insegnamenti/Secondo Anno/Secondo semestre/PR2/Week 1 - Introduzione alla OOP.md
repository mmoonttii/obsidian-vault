#Uni/Insegnamenti/Secondo_Anno/PR2 

Linguaggi
Macchine (Fisiche, intermedie, virtuali)
Livelli di astrazione
Tipizzazione
Paradigmi

## Cos'è un oggetto

Utilizziamo un linguaggio ad alto livello per poter essere vicini a come pensiamo il problema
Si utilizza il termine **classe** per indicare il tipo dell'oggetto.

Ogni oggetto ha una determinata posizione in memoria.

Il fatto che due oggetti siano dello stesso tipo, non implica che siano uguali, possono avere caratteristiche e valori diversi.

#Uni/Insegnamenti/Secondo_Anno/PR2 

Per ogni classe di oggetti si determina una serie di **attributi** che sono interessanti.
Ogni oggetto è detto essere una **istanza** di una classe
Gli attributi che un oggetto può avere sono gli stessi per ogni oggetto della classe: quindi è la classe a determinare quali attributi può avere un oggetto

Agli oggetti possiamo anche associare delle azioni che si possono svolgere con o su quell'oggetto. Queste azioni prendono il nome di **metodi**.

Una modellazione simile alla programmazione ad oggetti che vedremo in Java è fattibile anche in C, con le strutture etc... Quando, però, ad esempio definiamo una procedura sugli oggetti di quel tipo non abbiamo nulla che ci indica che quell'azione è dedicata a quegli oggetti

```C
struct Foglio{
	int larghezza;
	int altezza
}

void strappaFoglio (Foglio *foglio){
	foglio->altezza /= 2;
}

int main(){
	Foglio f = {30;50};
	strappaFoglio(&f);
	printf("%d", f.altezza);
}
```
```Java
class Foglio {
	int larghezza;
	int altezza;
	
	void strappa() {
		altezza = altezza/2;
	}
}

main {
Foglio f = new Foglio(30,50); // Questo prende il nome di costruttore dell'oggetto
f.strappa();
} 
```

La differenza principale tra struct e classi è che con le struct in qualsiasi parte della codebase è possibile sporcare lo stato della struttura, mentre con classi, attraverso l'**incapsulamento** possiamo regolare l'accesso agli attributi

I costruttori non hanno tipo di ritorno e il nome coincide con quello della classe
All'interno del costruttore posso controllare che quello che mi viene passato sia corretto oppure no (come tipo come valori) e gestire i casi contrari (anche interrompendo l'esecuzione)

```Java
class Foglio {
	int larghezza;
	int altezza;
	
	Foglio(int l, int a){
	larghezza = l;
	altezza = l
	}
	
	void strappa() {
		altezza = altezza/2;
	}
}
```

Adesso creiamo assieme la classe pennarello
`touch Pennarello.java`
`gedit Pennarello.java`

FARE LE GRAFFE COME LE FA FLA NON SI FANNO IN JAVA (e non si utilizzano nemmeno gli _ nei nomi delle cose)
```Java
/*
Anche i commenti lunghi si fanno come in C
*/
class Pennarello {
	// I commenti si fanno come in C
	String colore; // esistono le stringhe in Java!!! Però uooo è una classe
	float diametro;
	boolean haTappo; // Hanno usato il nome intero per i booleani
	
	Pennarello(String colore, float diametro) {
		haTappo = true;
		this.colore = colore; // utilizzare this. ci aiuta a distinguere tra il parametro e l'attributo a cui stiamo assegnando il valore
		this.diametro = diametro;
	}
	
	void rimuoviTappo() {
		haTappo = false;
	}
}
```

`touch Programma.java`
`gedit Programma.java`

```Java
public class Programma {
	public static void main (String[] args) {
		System.out.println("avvio del programma"); // Perchè è così complicato il print...
		Pennarello pennarello1 = new Pennarello("rosso", 1.1);
		Pennarello pennarello2 = new Pennarello("verde", 0.2);
		
		assert pennarello1.haTappo == true;
		assert pennarello2.haTappo == true;
		
		pennarello1.rimuoviTapoo();
		assert pennarello1.haTappo == false;
		
		// Nota come i metodi sono applicati agli oggetti, non alla classe, quindi il pennarello 2 ha ancora il tappo
		assert pennarello2.haTappo == true;
	}
}

```

# Lab
Quando compiliamo una classe con javac otteniamo un file `.class`, che contiene il bytecode riconosciuto dalla JVM
`javac Monitor.java`

Per runnare una classe non c'è bisogno di specificare l'estensione
`java Montior`