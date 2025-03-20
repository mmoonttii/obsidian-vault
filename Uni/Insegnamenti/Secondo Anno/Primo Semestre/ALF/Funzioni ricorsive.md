# Funzioni ricorsive

ID: ALF-12
Date: 19/11/2024
Status: Da revisionare

Facciamo un esempio, definendo la funzione fattoriale: 

$n! = \begin{cases}1 &&\text{ se } n = 0 \\ n \cdot (n-1)! &&\text { se } n > 0\end{cases}$

$fact=\{(0,1), (1,1), (2,2), (3,6), \dots\} \in \N \to \N$ 

Vediamo che il fattoriale è una funzione totale da N in N, non iniettiva, ne suriettiva

Proviamo a definirla con le regole di inferenza: ${\over (0,1)}, {(n-1, m)\over(n, y)}y=n \cdot m$

Proviamo a derivare la coppia (3,6)

$$
{{{{\over(0,m''= 1)}\over(1,m')}m'= 1\cdot m'=1\cdot 1 = 1\over(2,m)}m = 2 \cdot m' = 2\cdot 1 = 2\over (3,6)}6 = 3\cdot 2
$$

Questo è quello che avviene esattamente quando un calcolatore va a applicare una funzione ricorsiva.

ll problema è che questa forma è molto distante dalla definiione più matematica, scriviamo quindi la regola ${\over (0,1)}$ come $fact(0)=1$ e ${(n-1, m)\over(n, y)}y=n \cdot m$ come ${fact(n-1)=m\over fact(n)=n\cdot m}$

- Verifichiamo se questo insieme di regole di inferenza è una funzione oppure no${\over (0,0)}[R1], {(n-1, m)\over (n, m+2)}[R2], {(n-2, m)\over (n, m+3)}[R3]$
    
    
    $$
    {(0,0)\over{(1, 2)\over(2,4)}[R2]}[R2]
    $$
    
    $$
    {(0,0)\over{(2,3)}}[R3]
    $$
    
    L’interpretare questo insieme come una funzione sarebbe impossibile, perchè possiamo mappare 2 sia in 3 che in 4
    

Esiste però un modo sistematico per definire funzioni da regole di inferenza

$f: X \rightharpoonup Y\quad$consideriamo le regole di inferenza che definiscono $X$

- esempio: ${\over 0}, {n-1\over n}, {n-2\over n}$
    
    Il problema si verifica perchè possiamo definire un elemento dell’insieme attraverso due premesse differenti: quando si verifica questa condizione, l’insieme di regole è detto **non deterministico**
    
- ${\over 0}, {n-1 \over n}$ è un insieme di regole deterministico

In generale un insieme di regole è deterministico quando, se ho due regole con le stesse conseguenze, avrò necessariamente le stesse premesse

<aside>
📌

Se $X$ è l’insieme definito da un insieme di regole **deterministico $\mathcal R$**, si può definire una funzione $f \in X \rightharpoonup Y$ in questo modo:

- Sia $\displaystyle R \in \mathcal R: {x_1 \dots x_n \over y}A$
- Allora posso scrivere una nuova $\displaystyle R' \in \mathcal R' : {(x_1, z_1) \dots (x_n, z_n) \over (y, E(z_1, \dots, z_n,y))}$
</aside>

Proviamo a definire la funzione fattoriale in questa disciplina:

$R_0: {\over 0} \qquad R_0': {\over (0,1)}$

$R_1: {n-1\over n}\quad R_1': {(n-1,\, z) \over (n,\, n\cdot z)}$

È sempre necessario che il dominio sia definito **bene** dalle regole di inferenza