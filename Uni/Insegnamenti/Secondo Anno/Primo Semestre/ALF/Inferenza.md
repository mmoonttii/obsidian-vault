# Inferenza

ID: ALF-11
Date: 14/11/2024
Status: Da revisionare

<aside>
📌

$$
R = {x_1 \dots x_n \over y}A(x1, \dots, x_n, y)
$$

Se gli elementi $x_1, \dots, x_n$, sono parte dell’insieme e A è rispettata, allora anche y è parte dell’insieme

</aside>

Ma è vero che un insieme di regole di inferenza definisce un insieme?

<aside>
📌

Una **istanza di $R$** è una coppia $(a_1, \dots, a_n, b)$ tale che $a_1, \dots, a_n, b \in \mathbb D$, e $A (a_1, \dots, a_n, b)$ è vera

$\llbracket R \rrbracket = \{(a_1, \dots, a_n, b) | a_1, \dots, a_n, b \in \mathbb D \land A(a_1, \dots, a_n, b)\text{ è vera}\}$
 è l’insieme delle istanze di R

Se $\llbracket \mathcal R \rrbracket = U_{R\in \mathcal R} \llbracket R \rrbracket$ dove $\mathcal R$ è un insieme di regole di inferenza.

</aside>

$\mathcal R = \{{\over 0}, {x \over y}y=x+1\} \quad \mathbb{D = N}$

$\llbracket\mathcal R\rrbracket = \{{\over 0}, {0\over 1}, {1\over 2}, {2\over 3}, \dots\}$

<aside>
📌

$\^{\mathcal R} = \wp (\mathbb D) \to \wp(\mathbb D)$

$\^{\mathcal R}(X) = \{b | \exists R \in \mathcal R. \exists a_1, \dots, a_n \in X. {a_1, \dots, a_n \over b}\in \llbracket R \rrbracket\}$

</aside>

- $\mathcal R = \{{\over 0}, {x\over x+2}\} \quad \mathbb D = \R$
$\^{\mathcal R}(\{1\})= \{3, 0\}$ , perchè ${1\over 3} \in \llbracket {x \over x+2} \rrbracket$
    
    $\^{\mathcal R}$ è l’insieme delle conseguenze immediate, dati degli elementi che sono già aprte dell’insieme, troviamo altri elementi dell’insieme? Troviamo sempre l’assioma e i risultati di tutte le regole dove possiamo applicare gli elementi
    
    $\^{\mathcal R} (\{-2\}) = \{0\}$
    
    $\^{\mathcal R} (\{\emptyset\}) = \{0\}$
    
    $\^{\mathcal R} (\{1, 2, 3\}) = \{0, 3, 4, 5\}$
    
    $\^{\mathcal R} (\N) = \N \setminus \{1\}$
    
    > Notiamo che con $\N$, $\^{\mathcal R} (X) \subseteq X$
    > 
    - $\^{\mathcal R} (\Z) = \Z$
    
    $X = \{a_1, \dots, a_n\} \quad \^{\mathcal R} \ni a_n + 2$
    
    - $X = \N_p \Rightarrow \^{\mathcal R} (X) \subseteq X$: l’insieme dei numeri pari sembra l’insieme più piccolo che soddisfa queste regole di inferenza
    
    Perchè ci interessa l’insieme più piccolo: stiamo cercando di considerare l’insieme definito dalle regole di inferenza, ogni insieme che soddisfa la relazione notata è papabile. Dato che se ne hanno tanti, se non ce ne fosse uno giusto non avrebbe senso parlare di insieme definito dalle regole di inferenza: per questo “scegliamo” più piccolo di tutti
    

<aside>
📌

$f \in \wp(\mathbb D) \to \wp(\mathbb D)$: diciamo che $X$ è un **punto prefisso di $f$** se $f(X) \subseteq X$

$\^{\mathcal R} \subseteq X$

</aside>

A noi interessa il minimo dei punti prefissi di $\^\mathcal R$

- $\mathcal R = \{{x\ y\over x-y}\}\quad \mathbb D = \R$,
    
    $\^\mathcal{R}(\Z) = \Z$, allora $\Z$ è un punto prefisso di $\^\mathcal R$
    
    $-1 \in \^\mathcal{R}(\N) \nsubseteq \N$, quindi $\N$ non è un punto prefisso di $\^\mathcal R$
    
    $X = \{0\}\quad \^\mathcal{R}(\{0\}) = \{0\}$ è un punto prefisso
    
    $\^\mathcal{R}(\emptyset)= \emptyset$ è il punto prefisso **minimo di $\^\mathcal{R}$**
    

Questa definizione ribadisce il concetto che, quando non si ha un assioma, non si può dimostrare nulla, quindi si ha l’insieme vuoto

- $\mathcal{R} = \{{\over 10}, {x\quad y\over x+y}, {x\quad y\over x\cdot y}\},\quad \mathbb D = \N$
    - $\^\mathcal{R}(\emptyset) = \{10\}$
    - $\^\mathcal{R}(\{10\} = \{10, 20, 100\}$
    - $\^\mathcal{R}(\{10, 20, 100\}) = \{10, 20, 30, 110, 120, 100, 200, 1000, 2000, 10000\}$
    - Possiamo fare una congettura: se prendiamo $X = \{10\cdot n\, |\, n\in\N\setminus \{0\}\}$, allora $X$ è un punto prefisso, in particolare sarà il **minimo** punto prefisso di $\^\mathcal{R}(\emptyset) = \{10\}$
    - La terza regola è ridondante per definire questo insieme

$\mathcal R = \{{\over 0}, {x\over x+2}\}\qquad \qquad X$ è l’insieme definito da $\mathcal R$

$\^\mathcal R (Y) = \{0\} \cup \{x + 2\, |\, x \in Y\}$

1. $\{0\} \subseteq X$
2. $\{x+2 \, |\, x \in X\}$

Questi due vincoli insiemistici si riscrivono come $\{0\} \cup \{x + 2\, |\, x \in X\}\subseteq X$

Stiamo dicendo quindi che $\^\mathcal R (X) \subseteq X$

<aside>
📌

$f \in \wp (\mathbb D) \to \wp (\mathbb D)$ è **monotona** se $\forall X, Y. X \subseteq Y \Rightarrow f(X) \subseteq f (Y)$

**Lemma**: $\^\mathcal R$ è monotona, perchè se $X \subseteq Y \Rightarrow \^\mathcal R(X) \subseteq \^\mathcal R(Y)$

</aside>

<aside>
⚙

### Teorema di Knaster-Tarski:

Sia $f \in \wp(\mathbb D) \to \wp(\mathbb D)$ monotona.

Allora $f$ ammette un **minimo punto prefisso**, ovvero esiste $X \subseteq \mathbb D$ tale che:

1. $f(X) \subseteq X$ (X è un punto prefisso)
2. $f(X) \subseteq Y \Rightarrow X \subseteq Y$ (X è il più piccolo tra i punti prefissi)
</aside>

Quindi anche $\^\mathcal R$ ha un punto prefisso minimo

Se $\mathcal R$ è un insieme di regole di inferenza, allora chiamiamo **insieme induttivamente definito da $\mathcal R$**, il minimo punto prefisso di $\^\mathcal R$, o $fix(\^\mathcal R)$

# Il principio di induzione

## Principio di induzione sui numeri naturali

<aside>
📖

Supponiamo di voler dimostrare che $\forall n \in \N, Y(n)$

- caso **base: $Y(0)$**
- caso **induttivo: $\forall n \in \N. Y(n) \to Y(n+1)$**

$Y(0) \land \big(\forall n \in \N. Y(n) \to Y(n+1)\big)\to \forall n. Y(n)$

</aside>

<aside>
⚙

Il seguente teorema è una conseguenza immediata di Knaster-Tarski:

Sia $f \in \wp(\mathbb D) \to \wp(\mathbb D)$ monotona.

Allora, $\forall Y \in \mathbb D$:

$f(Y) \in Y \Rightarrow fix(f) \subseteq Y$

Questo teorema prende il nome di **principio di induzione**

</aside>

Per capire perchè lo chiamiamo così partiamo da un esempio

- $\mathcal R = \{{\over 0}, {x \over x+1}\}\qquad fix(\^\mathcal R) = \N$
    
    $\^\mathcal R(Y) \subseteq Y \Rightarrow fix(\^\mathcal R)=\N \subseteq Y$
    
    $\^\mathcal R : (\{0\} \cup \{x+1 | x \in Y\}) \subseteq Y \Rightarrow \N \subseteq Y$
    
    $0 \in Y \land \forall x. x \in Y \to x+1 \in Y \Rightarrow \forall n \in \N. n \in Y$
    
    Possiamo scrivere anche un insieme, come un predicato, vero se l’elemento è parte dell’insieme
    
    $Y(0) \land \forall x. Y(x) \to Y(x + 1) \Rightarrow \forall n\in N. Y(n)$
    
    Osserviamo che questa scrittura appena ottenuta partendo dal teorema di Knaster-Tarski, considerando il caso particolare delle regole di inferenza che definiscono l’insieme dei numeri naturali, non è altro che il principio di induzione.
    
    Quindi esiste, per tutti gli insiemi definibili con regole di inferenza, un “principio di induzione”