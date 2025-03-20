# Funzioni

ID: ALF-8
Date: 05/11/2024
Status: Da revisionare

Dati due insiemi $X$(insieme degli input) e $Y$(insieme degli output)

Una funzione è intuitivamente un oggetto che associa degli input a degli output

$f \subseteq X \times Y$(prodotto cartesiano) $= \{(x,y)\,|\, x \in X \land y \in Y\}$

Non tutti i sottoinsiemi del prodotto cartesiano sono delle funzioni

- $X = \{0,1\}\quad Y=\{2,3\}$
$X\times Y =\{(0,2),(0,3),(1,2),(1,3)\}$
$f=\{(0,2),(0,3)\}$ → f non può essere una funzione, perchè dato un input può produrre due output differenti. Per essere una funzione, una relazione ha bisogno che ad un input appartenga un solo output

<aside>
📌

$f \subseteq \{(x,y)\,|\, x \in X \land y \in Y\}$ è una funzione parziale da $X$ a $Y$ se

- $\forall\, a \in X, \forall\, b, b' \in Y.\, (a,b)\in f\land (a, b')\in f \to b = b'$

È una funzione parziale, perchè non è richiesto che tutti gli elementi dell’insieme degli input siano mappati

</aside>

<aside>
📌

Una funzione parziale $f$ è detta totale se  $\forall a \in X.\, \exists\, b\in Y\, |\, (a,b) \in f$

</aside>

- $dom(f) = \{x \in X\,|\,\exists y \in Y.(x,y)\in f\}$
- $ran(f) = \{y \in Y\, | \, \exists x \in X. (x,y) \in f\}$

## Costruttore di spazi di funzioni

Se X e Y sono insiemi,  X \times Y è prodotto cartesiano, X + Y somma disgiunta sono costruttori di insiemi

$X \rightharpoonup Y$ è l’insieme di tutte le funzioni parziali da $X$ in $Y$

$X \to Y$ è l’insieme di tutte le funzioni totali da $X$ in $Y$

Questi nuovi insiemi possono essere tranquillamente usati come insiemi di input e output di funzioni

- $X = \{0,1\}\quad Y=\{2,3\}$
$X \to Y = \{\{(0,2), (1, 2)\}, \{(0, 3), (1, 3)\},\\ \qquad\qquad\ \  \{(0,2), (1,3)\}, \{(0,3),(1,2)\} \}$
$X \rightharpoonup Y = (X \to Y) \cup\\\qquad \qquad\ \ \{\empty, \{(0,2)\}, \{(0,3)\},\\\qquad\qquad\quad \ \ \ \ \{(1,2)\}, \{(1,3)\}\ \}$
- Esistono anche, ovviamente, $X \to (Y \to X), (X\to Y) \to X$

Il poter costruire questi spazi di funzione, anche complessi sono utilizzati spesso nella programmazione funzionale.