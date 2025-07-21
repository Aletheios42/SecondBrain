**Tags:** #_Todo
#ToTag #ToLink 
- - -
Formalmente, sea N = {n₁, ..., nₘ} el conjunto de nodos y V el conjunto de valores posibles. Un protocolo de consenso debe garantizar:

Agreement: ∀ i,j ∈ N: decide(i) = decide(j)
Termination: ∀ i ∈ N: eventualmente decide(i) ≠ ⊥
Validity: Si decide(i) = v, entonces ∃ j ∈ N : propose(j,v)

// mirar
Problema de los 2 generales
Problema de los generales bizantinos
Paxos
Raft

# Protocolos de Consenso

- ### [[Proof of Work - POW]]
- ### [[Proof of Stake - POS]]
- ### [[Proof of History - POH]]
- - - 
## ***Sources:***
- Lamport, L. "The Part-Time Parliament" (Paxos) DOI: 10.1145/279227.279229
- Ongaro, D. "In Search of an Understandable Consensus Algorithm" (Raft) DOI: 10.5555/2643634.2643666
- https://www.youtube.com/watch?v=f1ZJPEKeTEY 
