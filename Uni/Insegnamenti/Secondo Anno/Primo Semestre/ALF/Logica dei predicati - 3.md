# Logica dei predicati - 3

ID: ALF-5
Date: 22/10/2024
Status: Da revisionare

# Semantica della logica dei predicati

Per dare una semantica alle formule della logica dei predicati utilizziamo i modelli $\mathbb{M = (D, I)}$, una coppia formata da $\mathbb{D}$ insieme non vuoto chiamato dominio e $\mathbb{I}$ una interpretazione.

Il dominio è l’universo dove vivono gli oggetti della formula, l’interpretazione il significato che viene associato a tutti i nomi di costanti variabili, funzioni e predicati.

Mostriamo due casi di esempio $\forall x. R(x,c)$, $R(x,c)$: nel primo caso la variabile $x$ non ha alcun significato preciso, perché indica ogni elemento del dominio; nel secondo caso la variabile $x$ non è quantificata da nulla

<aside>
📌

Definiamo un assegnamento una funzione $\mathbb{A}$ che mappa ogni variabile in elementi del dominio

</aside>

Quindi attraverso l’assegnamento possiamo anche assegnare un’interpretazione a variabili libere come nel seconod caso

<aside>
📌

Le formule atomiche sono dei predicati $P^n(t_1, \dots, t_n)$ applicati a tutti i termini, i predicati sono proprietà di questi termini

Utilizziamo la notazione $P(t_1, \dots, P_n)^{\mathbb{I, A}} = P^\mathbb{I}$ per dire che sto valutando la proprietà di questa formula atomica nell’interpretazione $\mathbb{I}$ e nell’assegnamento $\mathbb{A}$ e chiamiamo $P^\mathbb{I}$ il predicato nella data interpretazione dove possiamo applicare interpretazione e assgnamento a tutti it termini del predicato $P(t_1, \dots, P_n)^{\mathbb{I, A}} = P^\mathbb{I}(t_1^{\mathbb{I, A}}, \dots, t_n^{\mathbb{I, A}})$

</aside>

Facciamo degli esempi

- $\mathbb{D = N\quad 0^I} = 0 \quad S^\mathbb{I}\text{ è la funzione successore}\quad L^\mathbb{I} \text{ è la relazione} <$
    - $S(S(0))$ non è una formula, in quanto non può essere vera o falso, ma è un termine che attraverso un modello posso assegnargli una semantica:
    $S(S(0))^\mathbb{I, A} = S^\mathbb{I}(S^\mathbb{I}(0^\mathbb{I})) = 2$
    - $S(x)^\mathbb{I, A} = S^\mathbb{I}(x^\mathbb{A}) = S^\mathbb{I}(2) = 3 \qquad \text{dove }x^\mathbb{A} = 2$
    - $L(S(S(0)), S(x))^\mathbb{I, A} = 2 < 3 = 1 \qquad \text{dove }x^\mathbb{A} = 2$
- $\mathbb{D} \text{ è l’insieme degli insiemi finiti di numeri naturali}$
$0^\mathbb{I} = \emptyset \text{ (insieme vuoto)}$
$S^\mathbb{I} = X \cup m\text{ dove } m = \begin{cases} 0 && \text{ se } X = \emptyset \\ \max{X + 1} && \text{altrimenti}\end{cases}$
$L^\mathbb{I} = \subseteq$
$x^\mathbb{A} = \{1\}$
    - $L(S(S(0)), S(x)) = 0$
     $\{0,1\} \subseteq \{1,2\}$
- $\mathbb{D}\text{ è l'insieme delle parole dell'alfabeto \{0, 1\}}$
$0^\mathbb{I} = \text{ parola vuota }(\varepsilon)$
$S^\mathbb{I}(w) = w0$
$L^\mathbb{I}(w, w') = \text{“$w$ è prefisso di $w'$"}$
$x^\mathbb{A} = 00$
    - $L(S(S(0)), S(x))^\mathbb{I,A}$
    $L(00, 000) = 1$

Abbiamo mostrato come la stessa formula, cambiando modello la stessa formula può essere vera o falsa

$(\forall x. A)^\mathbb{I, A} = 1 \Leftrightarrow$ per ogni possibile valore di $x$ del dominio, quindi la formula sarà vera quando A sarà vera per ogni assegnamento di x nel domino $\Leftrightarrow A^\mathbb{I, B_1} = 1\  and\ A^\mathbb{I, B_2}\ and\ \dots$ dove $\mathbb{B_1, B_2, \dots}$ sono tutti i possibili assegnamenti a $x$. Bisogna fare attenzione che A poteva anch’essa fare assegnamenti.

$\forall x. P(x, y) \quad \mathbb{D} = \{5,7\} \quad y^\mathbb{A} = 5$
$= 1 \Leftrightarrow P(x,y)^\mathbb{I, B_1} = 1\ and\ P(x,y)^\mathbb{I, B_2} = 1$

$\mathbb{B_1 = \{y \mapsto 5, x\mapsto 5\}\quad B_2 = \{y\mapsto 5, y \mapsto 7\}}$ 

$\mathbb{B_i}$ sono $x$-varianti di $\mathbb{A}$

La semantica di $\forall, \exists$ sono delle estensioni agli insiemi, possibilmente infiniti, dominio di or e and

<aside>
📌

Possiamo adesso definire la semantica della logica dei predicati

- $(\lnot A)^\mathbb{I,A} = 1 - A^\mathbb{I,A}$
- $(A \land B)^\mathbb{I, A} = \min{(A^\mathbb{I, A}, B^\mathbb{I, A})}$
- $(A \lor B)^\mathbb{I, A} = \max{(A^\mathbb{I, A}, B^\mathbb{I, A})}$
- $(\forall x.\,A)^\mathbb{I, A} = \min\{A^\mathbb{I, B_i} |\mathbb{B_i\text{ è una $x$-variante di } A\}}$
- $(\exists x.\,A)^\mathbb{I, A} = \max\{A^\mathbb{I, B_i} |\mathbb{B_i\text{ è una $x$-variante di } A\}}$
</aside>

Dimostrare la verità di una formula dove compaiono i quantificatori non è sempre facile e automatizzabile perchè è necessario analizzare minimi e massimi su insiemi infiniti

<aside>
📌

Diciamo che una formula $A$ è:

- **soddisfacibile** in $\mathbb{M = (D, I)}$ se $A^\mathbb{I, A} = 1$ per **qualche** assegnamento $\mathbb{A}$
- **vera** in $\mathbb{M = (D, I)}$ se $A^\mathbb{I, A} = 1$ per **ogni** assegnamento $\mathbb{A}$
- **soddisfacibile** in assoluto se $A$ è soddisfacibile in **ogni modello $\mathbb{M}$**
- **VALIDA** se è **vera in ogni modello** $\mathbb{M}$
</aside>