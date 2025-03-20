#Uni/Insegnamenti/Secondo_Anno/CSMN 
Una volta che abbiamo il problema numerico ci preoccupiamo che sia **ben posto**
> Def (Hadamard):
> Un problema è ben posto se, in un determinato campo di definizione ammette una e una sola soluzione che dipende con continuità dai dati

Le caratteristiche di un problema ben posto sono quindi 3:
1. Esiste la soluzione
2. La soluzione è unica
3. La soluzione dipende con continuità dai dati

Ad esempio: Trovare $x \in \mathbb{Q}\ t.c.\ x^2 - 2 = 0$. 
Questo problema non è ben posto perché, uno la soluzione non è unica $x^2 = 2 \to x = \pm \sqrt{ 2 }$ 
Inoltre non è ben posto perché la soluzione non è $x \in \mathbb{Q}$

Quando un problema rispetta le prime due condizioni, ma non la terza, si dice **instabile**. Ovvero una piccola perturbazione nei dati, causa un grande scostamento nella soluzione, errori di misurazione o di memorizzazione.

L'instabilità di un problema **instabile** (o mal condizionato), si misura con il cosiddetto **numero di condizionamento**
Il nuemro di condizionamento può essere:
- **assoluto**: $K\ t.c\ | \delta x| \leq K |\delta d|$
- **relativo** $k\ t.c.\ \frac{|\delta x|}{|x|} \leq k \frac{|\delta d|}{|d|}$ : tiene in considerazione l'ordine di grandezza dei dati che stiamo considerando
Dove $∂d$ è l'errore sui dati, mentre $∂x$ è l'errore sulla soluzione ottenuta

Facciamo un esempio
"Prodotto di due numeri reali"
$a \qquad \qquad a +\delta a = \bar{ a}$
$b \qquad \qquad b + \delta b = \bar{b}$
Dati veri Dati misurati
$x = a \cdot b$
Sia noto che 
$\displaystyle \frac{|\delta a|}{a} = \frac{|\delta b|}{|b|} \leq \tau$ 
$\bar{x} = x + \delta x = \bar{a} \cdot \bar{b} = (a + \delta a) \cdot (b + \delta b) = ab + b\delta a + a\delta b + \delta a\delta b$