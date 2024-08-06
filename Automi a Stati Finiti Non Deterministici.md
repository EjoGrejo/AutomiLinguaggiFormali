# NFA
![[Screenshot 2024-03-16 alle 22.29.05.png]]
- È un esempio di *automa a stati finiti non deterministico:*
	- ci possono essere più transizioni con lo stesso simbolo
	- o simboli senza transizioni uscenti
	- ed $\epsilon$-transizioni che non consumano simboli
- Data una parola, *esistono più percorsi possibili*
- Si accetta se *esiste almeno un percorso accettante*

Un Automa a Stati Finiti Non Deterministico (NFA) è una quintupla:
		$A = ( Q, \sum, \delta, q_0, F)$
- $Q$ è un insieme finito di *stati*
- $\sum$ è un *alfabeto finito* che non contiene $\epsilon$. Definiamo $\sum_\epsilon = \sum \cup \{\epsilon\}$.
- $\delta : Q \times \sum_\epsilon \mapsto 2^Q$ è una *funzione di transizione* che prende in input $(q,a)$ e restituisce un *sottoinsieme di $Q$*
- $q_0 \in Q$ è lo *stato iniziale*
- $F \subseteq Q$ è un insieme di *stati finali*
## Computazione di un NFA
- Data una parola $w = w_1w_2...w_m$, dove $w_i \in \sum_\epsilon$ 
- Una *computazione* di un NFA $A$ con input $w$ è una sequenza di stati $r_0r_1....r_m$ che rispetta *2 condizioni*
	1. $r_0 = q_0$ (inizia dallo stato iniziale)
	2. $r_{i+1} \in \delta(r_i, w_{i+1})$ per ogni $i = 0,...,m-1$ (rispetta la funzione di transizione)
- Diciamo che una computazione *accetta* la parola $w$ se:
	3. La computazione *legge tutti i simboli della stringa*
	4. La computazione *termina in uno stato finale*
- A causa del nondeterminismo, *ci può essere più di una computazione* per ogni parola!
### Linguaggio accettato da un NFA
- Un NFA A *accetta* la parola $w$ se *esiste una computazione* che accetta $w$
- Un NFA A *rifiuta* la parola $w$ se *tutte le computazioni* rifiutano
- Formalmente, il *linguaggio accettato* da A è
		$L(A) = \{ w \in \sum^* | A$ accetta $w\}$
[[Operazioni sui linguaggi]]
# Equivalenza di [[Automi a Stati Finiti#DFA]] e NFA
- **NFA e DFA** _sono in grado di riconoscere gli stessi linguaggi_
- Per ogni NFA $N$ c'è un DFA $D$ tale che $L(D) = L(N)$ e viceversa
![[Screenshot 2024-03-16 alle 22.50.03.png]]
