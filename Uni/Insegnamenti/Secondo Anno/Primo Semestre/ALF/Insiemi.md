# Insiemi

ID: ALF-6
Date: 24/10/2024
Status: Da revisionare

# Set comprehension

E’ un formalismo per definre insiemi partendo da formule logiche

Sia $A$ una formula della logica dei predicati e assumiamo che dentro a possa apparire al massimo una variabile libera $x$: $A(x)$

$A(x) = x > 1 \land x < 5$ → x è libera

$B(x) = \forall x. x > 1$ → x è legata

Un insieme può essere definito usando la set comprehension con questa sintassi $\{x | A(x)\}$ e si legge l’insieme degli x tali che A sia vera per x

È necessario associare anche un modello M=(D,I), tutti gli x sono anche parte del dominio

L’insieme di tutti i $\mathbb{v \in D}$ tali che $A^\mathbb{I, A} = 1$ per $x^\mathbb{A} = v$

## Prodotto cartesiano

Sia $(a,b)$ una coppia di elementi $a \in X, b \in Y$, l’insieme dove abitano queste coppie è chimato prodotto cartesiano di $X$ e $Y$

$(a,b) \in X \times Y = \{(x,y)| x \in X \cap y \in Y\}$

$\pi_1(a,b) = a\qquad \pi_2(a,b) = b$ Sono dette proiezione sinistra e destra della coppia

## Somma disgiunta

$X + Y = (\{0\} \times X) \cup (\{1\}\times Y) = \{(0,x)|x\in X\} \cup \{(1,y)| y\in Y\}$

La simma disgiunta permette di unire gli elementi dell’insieme , senza però mescolarli aggiungendogli un’etichetta 0, 1