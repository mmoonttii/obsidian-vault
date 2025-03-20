# Logica Proposizionale classica 2

ID: ALF-2
Date: 03/10/2024
Status: Pronto

## Semantica della logica proposizionale classica

<aside>
📌

Ricordiamo dalla scorsa lezione i componenti della logica proposizionale classica:

- **lettere proposizionali: $P, Q, P_i, Q_j, \dots$** (che ****è un insieme infinito)
- **connettivi logici:** $\lnot,\ \land,\ \lor,\ \rightarrow$
- valori di verità: $0$ (falso), $1$ (vero)
</aside>

**Interpretazione $v$**: funzione che associa i valori di verità a tutte le lettere proposizionali

Data una formula proposizionale $A$ sintatticcamente corretta, si definisce la sua semantica fissando una sua **interpretazione *$v$***

<aside>
📌

Sia $v$ una funzione da lettere proposizionali a valori di verità $\{0, 1\}$.

Diciamo che $v$ è una **interpretazione** se:

- $v(\lnot A) = 1 - v(A)$
- $v(A \land B) = \min{\big(v(A),\ v(B)\big)}$
- $v(A \lor B) = \max{\big(v(A),\ v(B)\big)}$
- $v(A\rightarrow B)=\max{\big(1-v(A),\ v(B)\big)}$
</aside>

Ad esempio sia $A = \lnot\big((P\lor Q) \rightarrow (P\land Q)\big)$

$v(A) = 1 - v\big((P\lor Q) \rightarrow(P\land Q)\big)$

$= 1 - \max{\big(1 - v(P\lor Q),\ v(P \land Q)\big)}$

$= 1 - \max{\big(1 - \max{(v(P), v(Q)), \min{(v(P), v(Q))}}\big)}$

$= 1 - \max{\big(1 - \max{(1, 0), \min{(1, 0)}}\big)}$

$= 1 - \max{(1 - 1, 0)} = 1 - \max{(0,0)} = 1-0 = 1$ 

$v(P) = 1\\v(Q) = 0$

Data una formula e un’interpretazione delle sue lettere proposizionali possiamo ora valutarla.

---

Data in input solamente una formula, senza i valori delle sue lettere proposizionali possiamo classificarla in tre tipologie

<aside>
📌

Diciamo che una formula $A$ è:

- **soddisfacibile** se esiste un’interpretazione o più $v$ tale che $v(A) = 1$
- **insoddisfacibile** se non è soddisfacibile
- una **tautologia** se per ogni interpretazione $v$, $v(A) = 1$
</aside>

| $v(P)$ | $v(P \lor \lnot P)$ |
| --- | --- |
| 0 | 1 |
| 1 | 1 |

È un esempio di **tautologia** e dimostra il **principio del terzo escluso,** principio della logica classica, ma non scontato in tutte le logiche.

**True** è zucchero sintattico per una tautologia

| $v(P)$ | $v(Q)$ | $v(\lnot P \lor Q)$ |
| --- | --- | --- |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

Questa formula è equivalente all’implicazione ed è una formula **soddisfacibile** ma non è una tautologia

| $v(P)$ | $v(P\land \lnot P)$ |
| --- | --- |
| 0 | 0 |
| 1 | 0 |

Questo è un esempio di formula **insoddisfacibile**, è nota anche come ***legge di non contraddizione***

**False** è zucchero sintattico per questa formula

| $v(P)$ | $v(Q)$ | $(P \land \lnot P) \to Q$ |
| --- | --- | --- |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

- $(P\land \lnot P) \rightarrow Q$ è una tautologia, prende il nome di ***principio di esplosione*** e indica che assumendo il falso si può dedurre ciò che si vuole