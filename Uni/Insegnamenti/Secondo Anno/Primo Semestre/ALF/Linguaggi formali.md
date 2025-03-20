# Linguaggi formali

ID: ALF-14
Date: 28/11/2024
Status: Da revisionare

Ricordiamo che un sistema a transizione di stato è una tripla(quadrupla) $(Q,\Sigma, \to, q_o)$

$q_0 \xrightarrow{a_1} q_1 \xrightarrow{a_2} q_2 \xrightarrow{a_3} q_3$ che può essere sintetizzato in $q_0 \xrightarrow{a_1\,a_2\,a_3} q_3$

# Linguaggi formali

Ricordiamo cosa è un linguaggio:

- L’alfabeto $\Sigma$ del linguaggio: l’insieme **finito** dei simboli
- $\Sigma^*$: rappresenta l’insieme di tutte le sequenze **finite** di simboli in $\Sigma$: l’insieme delle **parole** su $\Sigma$
    
    $\displaystyle {\over \varepsilon}$, $\displaystyle{W \over aW} a\in \Sigma$: data una parola del linguaggio, è una parola del linguaggio $a$ concatenato $W$. $\varepsilon$ è la parola vuota, assioma di questo insieme di regole di inferenza
    

<aside>
📌 Un linguaggio $L$ sull’alfabeto $\Sigma$ è un sottoinsieme di $\Sigma^*$

</aside>

## Riconoscitore di linguaggi

Un riconoscitore di linguaggi è una macchina che prende in input una parola e restituisce Si se la parola appartiene al linguaggio, No se la parola non appartiene al linguaggio

- Data una parola $W = a_1a_2\dots a_n$
- La macchina leggerà la parola lettera per lettera
    
    $q_0 \xrightarrow{a_1} q_1 \xrightarrow{a_2} \dots \xrightarrow{a_n} q'$
    

Un LTS come quelli che abbiamo visto non è sufficiente per definire un riconoscitore di linguaggi, abbiamo bisogno di includere l’insieme $F \subseteq Q$, quindi LTS sarà una quintupla

Se $q' \in F$ allora $W \in L$, altrimenti se $q' \notin F$ allora $W \notin L$