#Uni/Insegnamenti/Secondo_Anno/PR2 
# News da Java 10: `var`
Da Java 10 è possibile definire e contestualmente assegnare il valore a una variabile, senza dover specificare il tipo che viene ottenuto per inferenza
```java
var s = "Ciao";
var r = new Rettangolo();

s.toUpperCase();
r.area();
```

# News da Java 9: JShell
Da Java 9 è stato introdotto il tool JShell, un REPL (Read-Eval-Print Loop), ovvero un  interprete che consente di testare velocemente espressioni o frammenti di codice provvedendo automaticamente alla compilazione ed esecuzione

# Interfacce
## Motivazioni

## Contratti

# Interfacce in Java
## Interfacce con classi abstract pubbliche

## Interfacce
Le interfacce sono quindi le Application Programming Interface (API) con cui si interagisce con un modulo software.
Nella programmazione ad oggetti, questi ultimi interagiscono con i metodi esposti.
I metodi dell'oggetto formato la sua interfaccia col mondo esterno

# Lab
>  28 apr
>  12 mag
>  Lezioni di recupero Lab PR2

## Eccezioni
Eventi che accadono durante l'esecuzione di un programma che possono porta

Anche le eccezioni sono oggetti

È possibile catturare un'eccezione e non bloccare l'esecuzione del programma utilizzando il blocco `try...catch`

Sia errori che eccezioni sono sottoclassi di Throwable (lanciabili).

Se un'eccezione eredita direttamente da Exception, è vista come checked e va gestita

## Classi astratte
...
## Interfacce
Le interfacce definiscono un "accordo" tra gruppi su come i componenti di un software devono lavorare tra loro

In Java le interfacce si comportano come classi con alcune particolarità:
- Tutte le variabili definite in un interfaccia sono `static` e `final` (costanti)
- Dichiarazioni di metodi, senza implementazione e `public` di default
- Implementazione di metodi statici
- Le interfacce non possono essere istanziate
- Possono essere **estese** da altre interfacce o **implementate** da altre classi
- Una classe può implementare **una o più interfacce**

Un'interfaccia può estendere più interfacce e una classe può implementare più interfacce: questo sorpassa il meccanismo di ereditarietà singola di Java

Le interfacce permettono il **polimorfismo** (trattare oggetti diversi con la stessa interfaccia)

Usiamo le classi astratte
- Se vogliamo condividere l'implementazione dei metodi
- Se vogliamo avere uno stato comune

Usiamo le interfacce
- Se le classi che implementiamo non sono necessariamente correlate
- Vogliamo specificare il comportamento delle classi senza preoccuparci dell'implementazione