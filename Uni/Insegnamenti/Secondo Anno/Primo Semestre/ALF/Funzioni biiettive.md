# Funzioni biiettive

ID: ALF-9
Date: 07/11/2024
Status: Da revisionare

O biiezioni

Ricordiamo quando una funz è iniettiva e quando suriettiva

$X$ insieme input $Y$ insieme degli output

<aside>
📌

$f\in X \rightharpoonup Y$ è 

- **iniettiva $\forall a, a' \in X. f(a) = f(a') \to a = a'$**
- **suriettiva $\forall b \in Y. \exists a \in X. f(a) = b$**
    - $f(a) = b$ è zucchero sinstattivo per $(a,b) \in f$
</aside>

<aside>
📌

Gli insiemi $X$ e $Y$ sono **equinumerosi** se esiste una funzione biiettiva $f \in X \to Y$

Lo indichiamo con $X \leftrightarrow Y$

</aside>

- $X = \{\text{Clarke Kent, Diana Prince, Peter Parker}\}$
$Y = \{\text{Superman, Wonder Woman, Spiderman}\}$
I due insiemi sono equinumerosi e possiamo quindi definre una funzione biiettiva tra i due
$f(\text{Clark Kent}) = \text{Superman}$
$f(\text{Diana Prince}) = \text{Wonder Woman}$
$f(\text{Peter Parker}) = \text{Spiderman}$

<aside>
📌

Dati due insiemi finiti, e quindi enumerabili
$X = \{a_1, \dots, a_n\}\quad |X| = n$
$Y = \{b_1, \dots, b_m\}\quad |Y| = m$
$n = m \Longleftrightarrow X \leftrightarrow Y$

Se i due insiemi sono equinumerosi, allora avranno la stessa cardinalità

</aside>

- Dati due insiemi $X$ e $Y$ arbitari, (potenzialmente infinit)
    
    $X \times Y \leftrightarrow Y \times X$?
    
    Se $X$ e $Y$ sono finiti $|X\times Y| = |X||Y| = |Y\times X|$, quindi sono equinumerosi
    

Torniamo al caso di insiemi infiniti

Proviamo applicando la definizione e troviamo una funzione

$(x,y) \in X\times Y$ , $(y,x) \in Y \times X$

$f(x,y) = (y,x)$ ⇒ questa funzione è facilmente dimostrabile essere biiettiva, quindi gli insiemi **sono** in biiezione

- $\N \leftrightarrow \Z$?
Si, possiamo trovare una $f \in \N \to \Z$
- $\N \leftrightarrow \N\times\N$?
Si, possiamo trovare una $f \in \N \to \N \times \N$
- $\N \leftrightarrow \{0,1\}^*$? (tutte le sequenze finite composte dagli elementi dell’insieme)
Si…
- $\N \leftrightarrow (\N \to \N)$? (insieme di tutte le funzioni da naturali a naturali)
Quì la risposta è complicata
Supponiamo sia vero, con un ragionamento per assurdo, allora possiamo trovare un modo per contarl
— vedi note a pagina 24 —
Siamo riusciti a definire una funzione $g \in \N \to \N$ diversa da tutte le funzioni che erano nell’insieme di tutte le funzioni $\N \to \N$, quindi siamo arrivati a una contraddizione, quindi la cardinalità di $(\N \times \N)$ è diversa dalla cardinalità di $\N$

Poichè $\N \leftrightarrow \{0,1\}^*$, ma non $\N \leftrightarrow (\N \to \N)$, allora NON $\{0,1\}^* \leftrightarrow (\N \to \N)$
Questa considerazioni ci fanno arrivare alla conclusione che esistono funzioni che non possono essere calcolate da programmi in informativa

$(X \times Y) \to Z \leftrightarrow X \to (Y \to Z)$

```ocaml
let fU (x,y) =
	if (x >= 0 && x <= 2 && y >= 0 && y <= 2) then (x + y) mod 3
	else failwith "undefined"
```

Questa funz ha tipo `fu: (int * int) -> int`

$f_U = \{ ((0,0),0), ((0,1),1), ((0,2), 2) \\ \qquad \ \ ((1,0),1), ((1,1),2), ((1,2),0),\\ \qquad \ \ ((2,0),2), ((2,1),0), ((2,2),1)\\ \} \in (X \times Y) \to Z))$

```ocaml
let fC x y =
	if (x >= 0 && x <= 2 && y >= 0 && y <= 2) then (x + y) mod 3
	else failwith "undefined"
```

Questa funz ha tipo `fc: int -> (int -> int)`

$f_C = \{(0, \{(0, 0), (1, 1), (2,2)\}), \\\qquad\ \ (1, \{(0,1),(1,2),(2,0)\}),\\ \ \qquad\ (2, \{(0,2), (1,0), (2,1)\})\\\} \in (X \to (Y \to Z))$