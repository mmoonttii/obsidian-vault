# Espressioni regolari

ID: ALF-17
Date: 10/12/2024
Status: Da revisionare

Si chiamano quindi linguaggi regolari i linguaggi riconoscibili da automi a stati finiti

Le espressioni regolari sono un insieme di esoressioni che descrivono linguaggi riconoscibili da automi a linguaggi finiti: la loro utilità è di descrivere in maniera più efficace per l’utilizzo con i calcolatori gli stessi linguaggi descritti dai FA

<aside>
📌

$$
\\\begin{split} E, E' \Coloneqq\emptyset & \text{ linguaggio vuoto}\\ \varepsilon & \text{ linguaggio con la sola parola vuota} \\ a & \text{ linguaggio con la sola parola } a\\ E + E' & \text{ unione tra due linguaggi}\\ E\ E' & \text{ concatenazione tra due linguaggi}\\ E^* & \text{ stella di Kleene}\end{split}
$$

</aside>

<aside>
📌

Semantica: $\mathcal{L}$ è la funzione da regex a linguaggio

A sinistra i simboli sono regex, a destra linguaggi

$$
\begin{split}\mathcal{L}(\emptyset) =&\ \emptyset\\ \mathcal{L}(\varepsilon) =&\ \{\varepsilon\}\\ \mathcal{L}(a) =&\ \{a\}\\ \mathcal{L}(E+E') =&\ \mathcal{L}(E) \cup \mathcal{L}(E')\\ \mathcal{L}(EE') =&\ \mathcal{L}(E) \mathcal{L}(E')\text{ dove } LL'=\{ww'| w \in L, w'\in L'\} \\ \mathcal{L}(E^*) =&\ \mathcal{L}(E)^*\text{ dove } L^* = \bigcup_{i \geq 0}L^i\text { e } L^{n+1} = LL^{n}, L^0 = \{\varepsilon\}\end{split}
$$

</aside>

- $E = 0 + 11$
    
    $\mathcal{L}(E)= \mathcal{L}(0+11) = \mathcal{L}(0) \cup \mathcal{L}(11) = \{0\}\cup (\mathcal{L}(1)\mathcal{L}(1)) = \{0\}\cup(\{1\}\{1\}) = \{0\}\cup\{11\} = \{0, 11\}$
    
- $E = (0+11)^*$
    
    $\mathcal{L}(E) = \{0, 11\}^*$
    $\{0,11\}^0 = \varepsilon\\\{0,11\}^1 = \{0,11\}\\ \{0,11\}^2 = \{0,11\}\{0,11\} = \{00, 011, 110, 1111\}$
    
- $L_{01}= \{w01| w \in \{0,1\}^*\}$
    
    $E = (0+1)^*01$
    
- $L_{alt}$: il linguaggio dove 0 e 1 devono essere alternati
    
    $L_{alt} = \{\varepsilon, 0, 1, 01, 10, 010, 1010, 0101, 1010, \dots\}$
    
    $$
    ⁍
    $$
    
    $$
    {{{{\over0}\over 01}\over010}\over 0101}
    $$
    
    $$
    {{{\over 01}\over011}\over 0110}
    $$
    
    $E_{alt}=(\varepsilon + 1)(01)^*(\varepsilon + 0)$
    

### Algoritmo di Thompson: da regex a FSA

Per comodità utilizza l’invariante che l’automa ottenuto ha uno stato iniziale e finale diversi tra loro

INPUT: $E=(\emptyset)$

OUTPUT: ${\cal A} (E) = A$

### Algoritmo di state eliminationn $\mathcal E$: da FSA a Regex

Si basa su un estensione degli FSA dove le etichette possono essere espressioni regolari arbitrarie