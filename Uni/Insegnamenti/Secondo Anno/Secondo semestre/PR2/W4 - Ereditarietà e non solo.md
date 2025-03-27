#Uni/Insegnamenti/Secondo_Anno/PR2 
# Wrapping classes, autoboxing e unboxing
Ogni tipo primitivo ha associata una classe corrispondente, detta [wrapper](https://en.wikipedia.org/wiki/Primitive_wrapper_class).
Avere queste classe associate ci permette di creare array composti da oggetti generici, tra cui elementi dei tipi primitivi

| Tipo primitivo | Classe wrapper |
| -------------- | -------------- |
| `byte`         | `Byte`         |
| `short`        | `Short`        |
| `int`          | `Integer`      |
| `long`         | `Long`         |
| `float`        | `Float`        |
| `double`       | `Double`       |
| `char`         | `Character`    |
| `boolean`      | `Boolean`      |
### Da un tipo primitivo creare un oggetto
```java
int i = 5;
Integer j = new Integer(i);
Integer j = 5; //Autoboxing
```
L'**autoboxing** è una tecnica che permette di assegnare tipi primitivi agli oggetti della classe wrapper corrispondente.

### Da una classe wrapper a un tipo primitivo
```java
Integer J = new Integer(5);
int i = j.intValue();
int i = j; //Unboxing
```
L'**unboxing** è la tecnica opposta all'autoboxing, che permette di assegnare al tipo primitivo, il valore contenuto della classe corrispondente in maniera più breve.

# Classi astratte
A volte, nella gerarchia delle classi, si ha bisogno di specificare l'**interfaccia pubblica** (la firma dei metodi) ma non si ha la possibilità di specificarne l'implementazione.

Ad esempio per la classe `FiguraGeometricaChiusa` avremo sempre il metodo `area()`, ma questo può essere definito solamente dalle diverse sottoclassi.
La soluzione a questo problema è dichiarare la classe e i metodi necessari come **`abstract`**.

Una classe può essere dichiarata abstract anche se ha tutti i metodi implementati. In questo caso si evita di poter costruire oggetti di quello specifico tipo.

```java
abstract public class FiguraGeometricaChiusa {
	abstract public double area();
}
```

> Spesso il nome di una classe astratta inizia con "*Abstract*" (es. `AbstractList`)
# Ereditarietà e visibilità
Facendo l'override di un metodo di una superclasse possiamo assegnare a questo solamente visibilità maggiore o uguale rispetto al metodo offuscato.

Non è possibile fare l'override di attributi, la sottoclasse eredita dalla superclasse solo gli attributi con sufficiente visibilità: quando li ridefiniamo stiamo nascondendo l'attributo della superclasse (**shdowing**)

# `static`
La parola chiave `static` serve a taggare qualcosa come (informalmente) "*slegato da uno specifico oggetto*".
Metodi e attributi possono essere dichiarati `static`, diventando quindi **attributi/metodi di classe** (anziché di istanza o di oggetto)

### `public static void main()`
Quando chiamiamo una classe con il metodo main, l'interprete non deve creare un oggetto della classe chiamata ma lo vogliamo utilizzare come entry point 

Se dovessimo utilizzare solo metodi static, staremmo scrivendo funzioni di programmazione imperativo-procedurale

> Dentro un metodo `static` non ha significato utilizzare la keyword `this` perché non ci stiamo riferendo ad alcun oggetto