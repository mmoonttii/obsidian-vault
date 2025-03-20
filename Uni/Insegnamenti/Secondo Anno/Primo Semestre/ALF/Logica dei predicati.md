# Logica dei predicati

ID: ALF-3
Date: 10/10/2024
Status: Pronto

Consideriamo un mondo distopico di amore unidirezionale, dove ognuno ama qualcuno, ma quell’amore non è reciprocato dall’amato. Questa situazione può essere codificata in logica proposizionale in questo modo:

> A: *“Tutti amano qualcuno”*
B: *“Nessuno ama chi lo ama”*
> 

Semplificando la nostra conoscenza in queste due proposizioni, perdiamo le specifiche informazioni sulle relazioni tra individui

La logica proposizionale non tratta delle relazioni ma solamente di fatti veri o falsi.

La logica dei predicati permette di esprimere cose vere o false che riguardano elementi di un certo universo in maniera più granulare.

Introduciamo quindi la logica dei predicati con la rappresentazione sintattica degli oggetti di un universo:

- **costanti $a, b, c, \dots$**, identificano **unicamente** gli oggetti dell’universo
- **variabili** $x, y, \dots$, identificano un oggetto generico
- **funzioni** $f, g, \dots$, identificano oggetti in relazione ad altri oggetti
- **predicati $P, Q, \dots$**, rappresentano relazioni tra oggetti

Nella logica dei predicati non esistono le lettere proposizionali e le *formule atomiche* sono ottenute applicando predicati ai termini

In una funzione o in un predicato si indica in apice il numero di argomenti che accettano $f^1, g^2, P^1, Q^2, \dots$ e prende il nome di **arità**

<aside>
📌

L’insieme dei **termini** è definito dalle seguenti regole:

1. ogni costante $c$ è un termine
2. ogni variabile $x$ è un termine
3. se $t_1, \dots, t_n$ sono termini e $f^n$ è una funzione, allora $f(t_1, \dots, t_n)$ è un termine
4. Nient’altro è un termine
</aside>

Con questo linguaggio possiamo rappresentare gli oggetti dell’universo, e quindi non possiamo determinare alcuna verità o falsità, quindi introduciamo proprietà di oggetti e relaizoni tra essi, assimilati con il nome di **predicato**. Il predicato è qualcosa che può essere vero o falso e riguarda più oggetti dell’universo. 

Possiamo introdurre i **connettivi logici**: $\lnot, \land, \lor, \to$ e introduciamo anche i quantificatori:

- $\forall\, x . A$ quantificatore universale (per tutti gli elementi dell’universo $x$ vale A)
- $\exists\, x.A$ quantificatore esistenziale

<aside>
📌

L’insieme delle **formule** della logica dei predicati è definito dalle regole:

1. se $t_1, \dots, t_n$ sono dei termini e $P^n$ è un predicato, allora $P(t_1, \dots, t_n)$ è una formula
2. se $A, B$ sono formule, allora $(\lnot A), (A \land B), (A \lor B), (A \to B)$ sono formule
3. se $A$ è una formula, allora $(\forall\, x.A), (\exists\, x.A)$ sono formule
4. nient’altro è una formula
</aside>