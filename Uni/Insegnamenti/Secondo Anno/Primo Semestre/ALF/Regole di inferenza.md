# Regole di inferenza

ID: ALF-10
Date: 12/11/2024
Status: Da revisionare

# Regole di inferenza

Sono un formalismo utilizzato per definire insiemi che possiamo utilizzare oltre alla *set comprehension*

Abbiamo bisogno di utilizzare un altro formalismo, perchè la definizione per comprensione non è molto “operazionale” e facilmente utilizzabile da un calcolatore

Una regola di inferenza è un oggetto con la forma

$$
{{x_1\dots x_n}\over {y}} A
$$

Sopra la riga abbiamo $n$ variabili, sotto un’altra variabile e a destra della regola una formula per il calcolo del predicato

La regola ha un significato intuitivo, le variabili hanno senso quando sostiutite con elementi di un insieme. 

$\text{Dominio } \N$: Vogliamo definire un insieme $X \subseteq \N$:

$\displaystyle{\over y} y= 0$: Lasciando il piano di sopra vuoto, stiamo semplicemente mettendo 0 variabili al piano di sopra. Questa regola dice che $0 \in X$. Questa regola senza premesse prende il nome di **assioma**

$\displaystyle{x\over y}\, y= x+2$: $\displaystyle {0 \over 2} 2 = 0+2$, quindi $2 \in X$, $\displaystyle {2\over4}4 = 2+2$

Quindi con le regole $\displaystyle {\over y} y = 0\, [R1]$ e $\displaystyle {x\over y} y = x+2 \,[R2]$ stiamo definendo l’insieme dei numeri pari

# Albero di derivazione

<aside>
📌

Un albero di derivazione è una dimostrazione che un certo elemento appartiene all’insieme $a \in X$

</aside>

- Ad es. verifichiamo che 4 in numeri pari
    
    $$
    \displaystyle{{{ \over 0}[R1] \over 2 }[R2] \over 4[R2]}
    $$
    
- Proviamo a verificare 5
    
    $$
    \displaystyle{{{ ? \over 1}[R?] \over 3 }[R2] \over 5[R2]}
    $$
    
    Dato che non esistono modi di chiudere l’albero $5 \notin X$
    
    Se $D = \R$
    
    $$
    \displaystyle{{{{{ \over -3}[R2]\over -1}[R2] \over 1}[R2] \over 3 }[R2] \over 5[R2]}
    $$
    
    Non raggiungeremo mai un assioma, una foglia, quindi $5 \notin X_\R$
    

## Zucchero sintattico

- Quando una condizione a lato determina $y$ univocamente possiamo scrivere direttamente il valore univoco sotto

$$
\displaystyle{\over 0} == {\over y}y=0
$$

$$
\displaystyle{x \over x+2} == {x \over y} y= x+2
$$

Vediamo altri set di regole e proviamo ad applicarli $D = \N$

$$
{\over 0}[R3] \qquad {\over 2}[R4] \qquad {x\quad y\over x+y}[R5]
$$

$$
\displaystyle{{{{\over 2}[R4]\ {{{\over 2}[R4]\ {\over 2}[R4]}\over 4}[R5]}\over6}[R5]{\over6}\over 12}[R5]
$$

Queste regole definiscono sempre l’insieme dei numeri pari

Proviamo questa regola

$$
{x \over x+1}
$$

Non abbiamo il caso dove abbiamo un assioma di base, quindi l’insieme che definisce è l’insieme vuoto: qualunque insieme di regole di inferenza che non ha un assioma definisce l’insieme vuoto

# Tagged unions in OCaml

```ocaml
type t = T0 | T1 of int
```

Questa è una tagged unions di OCaml che contiene T0 che è di tipo unit e T1 a cui posso assegnare qualunque intero

## Recursive tagged unions

```ocaml
type t = T0 | T1 of t
```

Utilizziamo il tipo appena definito nella definizione del tipo stesso

I valori in questo tipo abbiamo T0 e T1 che è di tipo t, quindi T1 T0 è del tipo t

T1 (T1 T0) è tipo t

T0 è come un assioma nelle regole di inferenza

T1 of t è come una regola $\displaystyle{x \over T1\ x}$

$$
{{{{\over T0}\over T1\ T0}\over T1(T1\ T0)}\over T1(T1(T1\ T0))}
$$