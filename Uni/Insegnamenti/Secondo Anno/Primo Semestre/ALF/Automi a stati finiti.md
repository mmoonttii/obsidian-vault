# Automi a stati finiti

ID: ALF-15
Date: 03/12/2024
Status: Da revisionare

<aside>
📌

Ricordiamo il passaggio da LTS a Language recognizers

$(Q,\Sigma, \to)\qquad A=(Q, \Sigma, \to, q_0, F)$

$\qquad\qquad\qquad\ \mathcal{L}(A) = \{w \in \Sigma^*|\exists q' \in F. q_0\xrightarrow{w}q'\}$

</aside>

<aside>
📌

Sono detti **finite automata, automi a stati finiti**, Language recognizers con $Q$ finito

</aside>

Nel mondo degli automi a stati finiti ne esistono diversi tipi a seconda delle realzioni

### Automi a stati finiti con relazioni deterministiche - DFA

q -a→ q’, q -a→ q’’ con q’ ≠ q’’ NO

<aside>
📌

Sono detti **deterministic finite automata (DFA)** gli automi a stati finiti dove le relazioni di transizione sono deterministiche

</aside>

Il riconoscitore di linguaggi per il linguaggio $\mathcal{L} = \{w \in \Sigma^* | |w|_1 >0\}$ che abbiamo visto la volta scorsa è un DFA 

Gli automi a stati finiti hanno molteplici applicazioni oltre all’utilizzo come language recognizers: quello che abbiamo visto è solo una piccola infarinatura