# Intro e Logica proposizionale classica

“*Fondamenti di software*”

Programmazione funzionale $\Longleftrightarrow$ superamento dell’esame

---

*“Capire come sviluppare software che funziona bene”*

Un **buon software** deve essere:

- **corretto** (coerenza dell’implementazione con una specifica di riferimento)
- **sicuro** (il software deve funzionare bene e resistere anche quando usato in maniera malevola)

---

# Logica proposizionale (classica)

La logica proposizionale studia le proposizioni, ovvero idee che possono rappresentare fatti ed essere ***veri o falsi***.

> *“Joker è nemico di Batman”*
> 

 È possibile non essere a conoscenza del valore di verità della proposizione, ma è certo che ricadrà in uno dei due casi.

> *“Io sono Batman”*
> 

Queste proposizioni che non possono essere scomposte in componenti più piccole e sono dette ***proposizioni atomiche***. 

Per comporre più proposizioni atomiche tra di loro si utilizzano i **connettivi logici** ($\text{and }\land$, $\text{or }\lor$, $\text{not }\lnot$, $\text{implies }\rightarrow$)

> *“Le rose sono rosse e le viole sono blu”*
> 

## L’evoluzione della logica

Nonostante la matematica si sia evoluta attraverso i millenni continuamente, la logica, dopo Aristotele, non ha avuto sviluppi e veniva studiata solamente attraverso lunghi discorsi in linguaggio naturale, fino alla metà dell’800.

Leibniz aveva trovato un modo per ricondurre il ragionamento al puro calcolo ma non approfondì gli studi che vennero ripresi da George Boole.

## Sintassi della logica proposizionale

Per evitare le ambiguità e le complessità del linguaggio naturale, esprimiamo le frasi delle proposizioni logiche con un linguaggio formale che definisce precisamente tutte e solamente le frasi composte correttamente.

Le frasi di questo linguaggio formale sono chiamate ***formule proposizionali***

Chiamiamo ***lettere proposizionali*** $P, Q, R', Q_7, \dots$ delle variabili che possono essere sostituite da proposizioni.

<aside>
📌

L’insieme delle ***formule proposizionali*** è definito dalle seguenti regole:

- tutte le lettere proposizionali $P, Q, R, P', Q_7, \dots$ sono formule;
- se $A, B$ sono formule proposizionali, allora $(\lnot A),\ (A \land B),\ (A \lor B),\ (A \rightarrow B)$ sono formule proposizionali;
- nient’altro è una formula proposizionale
</aside>

Per evitare di utilizzare sempre le parentesi si stabiliscono le priorità dei connettivi  $\lnot\ >\ \land\ >\ \lor\ >\ \rightarrow$ ( dove $\lnot$ ha la priorità massima)

| $A$ | $B$  | $\lnot A$  | $A \land B$  | $A \lor B$  | $A \rightarrow B$  |
| --- | --- | --- | --- | --- | --- |
| 0 | 0 | 1 | 0 | 0 | 1 |
| 0 | 1 | 1 | 0 | 1 | 1 |
| 1 | 0 | 0 | 0 | 1 | 0 |
| 1 | 1 | 0 | 1 | 1 | 1 |

Implicazione è falsa solo quando l’antecedente è vero e la conseguenza falsa