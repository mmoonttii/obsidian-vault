# Logica dei predicati 2

ID: ALF-4
Date: 17/10/2024
Status: Da revisionare

# Semantica della logica dei predicati

Facciamo un po’ di ragionamenti

Ricordiamo che la base di questa logica sono le formule atomiche: $P^n(t_1, \dots, t_n)$ predicati di arità $n$ con $n$ termini

I Termini possono essere $x$ vzriabili, $c$ costanti, $f^n(t_1,\dots, t_n)$ funzioni di arità n applicati a n termini. Sono i modi di cui possiamo parlare degli elementi del nostro universo

$0 < 1 + 0$ dove $0,1$ sono costanti, $+$ è una fun di arità 2 e $<$ un predicato: in modo più logichese $LT^2(0, add^2(0, 1))$

<aside>
📌

Un Modello $\mathbb{M} = (\mathbb{D, I})$ dove

- $\mathbb{D}$ è un insieme non vuoto detto **dominio** (universo delle costnti)
- $\mathbb{I}$ è una **interpretazione** dei nomi di costanti, funzioni, predicati
    - se $c$ è un nome di costante, allora $c^{\mathbb{I}} \in \mathbb{D}$ (c è un nome, simbolo stringa, attraverso l’interpretazione prende il significato)
    - se $f^n$ è un nome di funzione, allora $f^{\mathbb{I}} \in \mathbb{D^n \to D}$
    - se $P^n$ è un nome di predicato, allora $P^\mathbb{I} \subseteq \mathbb{D^N}$
</aside>

Dato un modello $\mathbb{M = (D, I)}$

- $\mathbb{D= \{0,1,2,\dots\}}$
- $\mathbb{0^I = 0\quad 1^I = 1}$ (Il primo 0 e 1 sono simboli, il secondo sono i numeri naturali veri e propri elementi del dominio)
- $add$ è l’addizione tra numeri naturali $\mathbb{N \times N \to N}$
- $LT = \{(x, y) \in \N\times \N\,|\, x < y\} \subseteq \N \times \N$

Dato il modello possiamo adesso verificare la verità o la falsità della formula: la formula è vera in questo modello

---

$\mathbb{D} =$ insieme delle stringhe di 0 e 1

$\mathbb{0^I = 0\quad 1^I = 1}$

$add =$ concattenazione di stringhe

$LT =$ prefisso $LT(x, y)$ se $x$ è un prefisso di $y$

In questo modello la formula precedente non è vera

---

$P(t) \lor \lnot P(t)$ questa formula, qualunque sia il termine $t$, è sempre vera, per il principio del terzo escluso, questa è una formula che non dipende dalla scelta del modello: diremo quindi che è una formula **valida**, equivalenti delle tautologie della logica proposizionale

$\forall x. P(x) \lor \lnot P(x)$ anche questa formula, che utilizza i quantificatori, è valida

$\forall x. \forall y. P(x) \lor \lnot P(y)$ questa formula non è valida (non è vera in ogni possibile modello), per dimostrarla è sufficiente mostrare un modello dove è falsa: ad esempio

$\mathbb{D} = \{2, 3\}$

$P^\mathbb{I} = \{2\}$

In questo modello  $P(2)$ è vero e $P(3)$ è falso, ad esempio preso $x = 3$ e $y = 2$ è falsa, però esistono anche modelli dove è vera

---

Cerchiamo per ogni formula un modello dove è vera e dove è falsa

$\forall x. (R(0,x) \to R(x, 0))$

VERA

$\mathbb{D} = \{5\}$

$0^\mathbb{I} = 5$

$\R^\mathbb{I} \subseteq \mathbb{D^2 = D\times D} = \{(5,5)\}$ 

$\R^\mathbb{I} = \emptyset : x = 5 : \R^\mathbb{I}(0^\mathbb{I}, 5) \to \R^\mathbb{I}(x, 0^\mathbb{I}) \Leftrightarrow R^\mathbb{I}(5,5) \to R^\mathbb{I}(5,5)$

$\R^\mathbb{I} = \{(5,5)\}$

FALSA

$\mathbb{D} = \{5, 7\}$

$0^\mathbb{I} = 5$

$R^\mathbb{I}(0^\mathbb{I}, x) \text{ vero } \Leftrightarrow R^\mathbb{I}(5, x)\text{ vero } \Leftrightarrow R^\mathbb{I}(5, 7) \text{ vero }$

$R^\mathbb{I}(x, 0^\mathbb{I}) \text{ falso } \Leftrightarrow R^\mathbb{I}(x, 5)\text{ falso } \Leftrightarrow R^\mathbb{I}(7, 5) \text{ falso }$

Quindi $R^\mathbb{I} = \{(5,7)\} \subseteq \mathbb{D^2}$

---

$\exists x. (R(0,x) \lor R(x, 0))$

VERA:

$\mathbb{D} = \{5\}$

$0^\mathbb{I} = 5$

$R^\mathbb{I} = \{(5,5)\}$

$x = 5 : R^\mathbb{I}(5,5) \lor R^\mathbb{I}(5,5)$

FALSA:

\mathbb{D} = \{\}

0^\mathbb{I} =

$R^\mathbb{I} = \emptyset$

---

$\forall x. (R(x) \to R(f(x))$

VERA:

$\mathbb{D} = \{5\}$

$R^\mathbb{I} = \emptyset$

FALSA:

$\mathbb{D} = \{5, 7\}$

$R^\mathbb{I}= \{5\}$

$f^\mathbb{I}(5) = 7$

$x = 5 : R^\mathbb{I}(5) \to R^\mathbb{I}(f^\mathbb{I}(5)) : V \to R^\mathbb{I}(7) : V \to F : F$ 

Nella logica proposizionale, decidere se una formula è tautologia, sat o unsat è una domanda alla quale si può dare una risposta algoritmica. Noi utilizziamo l’algoritmo di enumerazione dei diversi casi e analizziamo i risultati. In logica dei predicati, trovare un algoritmo che sappia dire che una formula è valida in qualunque modello è impossibile, perchè i possibili modelli sono infiniti

---

\exists x. (R(f(n) \land \lnot R(x))

VERA:

$\mathbb{D} = \{5,7\}$

$\R = \{7\}$

$f(5) = 7$

$x = 5 : R(f(5)) \Leftrightarrow R(7) \text{ vera}$

$R(5) \text{ falsa}$

FALSA:

$\mathbb{D} = \{5\}$

$\R = \emptyset$