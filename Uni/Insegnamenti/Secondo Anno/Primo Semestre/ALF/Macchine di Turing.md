# Macchine di Turing

Le macchine di Turing, introdotte in un articolo del matematico Alan Turing nel 1936

Per Turing dovevano essere uno strumento per risolvere il “problema della decisione” (“*Entscheidungsproblem*“) posto da Hilbert. Questo problema era considerato dal Hilbert come risolvibile nel futuro. Il problema consisteva nel produrre un algoritmo per verificare la validità delle formule della logica dei predicati. Questo era utile perché si era trovato un meccanismo per scrivere in logica dei predicati i teoremi matematici, e quindi si sarebbe potuto ridurre tutta la matematica al codificare una congettura in una formula e avviare il programma di verifica.

Al tempo i calcolatori disponibili erano i primi calcolatori meccanici come quella di Pascal: quindi la risoluzione del problema di Hilbert si sarebbe limitato all’algoritmo, in quanto non erano disponibili macchine che potessero risolverlo.

Turing, quando dimostrò che non era possibile risolvere questo problema, pensava di essere arrivato secondo, in quanto Church era arrivato a conclusioni simili. Solo successivamente si comprese che la dimostrazione vera era quella di Alan Turing, perché riuscì a dare una definizione di algoritmo più generale.

Turing voleva dimostrare l’inesistenza di un algoritmo per risolvere il problema. Le macchine di Turing sono state create per essere la definizione più generale possibile di algoritmo.

Le semplificazioni lo portarono alla creazione di un sistema semplice, basato su un nastro infinitamente lungo, diviso in celle, all’interno del quale si possono scrivere una serie di simboli, appartenenti a un insieme finito e una  che può leggere un solo simbolo alla volta, e una volta letto può sovrascriverò e può spostarsi a destra o sinistra. La testina è controllata da un automa a stati finiti. Turing assume che l’automa sia a Stati finiti, per la finitezza del cervello umano.

[Turing machine visualization](http://turingmachine.io)

```python
# Questa macchina esegue la somma di due numeri in unario separati da un blank
input: '11_111' #nastro in ingresso
blank: '_' # simbolo dello spazio vuoto
start state: q0 # nome stato iniziale
table:
  q0:
    1: {write: 1, R: q0}
    _: {write: 1, R: q1}
  q1:
    1: {write: 1, R: q1}
    _: {write: _, L: q2}
  q2:
    1: {write: _, R: h}
  h:
```

![[IMG_0411.jpeg]]

Questa macchina controlla che la parola input appartiene al linguaggio 0*1*

Una macchina di Turing può riconoscere anche le parole del linguaggio 0^k1^k

### Definizione formale

<aside>
📌

Una macchina di Turing è una tupla $(Q, \Sigma, \delta, q_0)$, dove

- $Q$ è un insieme **finito** di stati, $h \notin Q$
- $\Sigma$ è un insieme **finito** di simboli
- $\delta \in Q \times \Sigma \to (Q \cup \{h\}) \times \Sigma \times (l, r, *)$
- $q_0 \in Q$ è lo stato iniziale
</aside>

### Semantica

<aside>
📌

**Configurazione**: uno stato dell’automa più una rappresentazione del nastro, che indica anche dove si trova la testina

</aside>

Facciamo la supposizione che inizialmente solamente una porzione del nastro finita sia scritta 

poiché il nastro è finito, lo possiamo rappresentare come una coppia di parole, una parte è la parte a sinistra della testina, la seconda parte della coppia, i simboli rimanenti, il simbolo indicato dalla testina e quelli tutti a destra

<aside>
📌

</aside>