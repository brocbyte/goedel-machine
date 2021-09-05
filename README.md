## Gödel machines

Can we build it?

## Notes

- universal problem solvers = solver (environment) + proof-searcher (rewrite itself for good)

- p(1) - the initial software = e(1) + proof-search technique

- e(1) - the original policy for interacting with the environment (problem-solver)

### Proof searcher

- makes pairs (switchprog, proof) until it finds a proof of a "target theorem", which says:\
  _"the immediate rewrite of p through current program switchprog on the given machine implies higher utility than leaving p as is"_\
  ==> (we have global optimality from here)

- uses online extension of Universal Search (Levin search?)

- an axiomatic system A encoded in p(1):
  <ol type="a">
  <li> instruction semantics </li>
  <li> the initial program p(1) itself </li>
  <li> stochastic environmantal properties </li>
  <li> the formal utility function u </li>
  </ol>

- ignores those self-improvements whose effectiveness it cannot prove

### Links

- Main page: https://people.idsia.ch/~juergen/goedelmachine.html

- Concept: https://arxiv.org/pdf/cs/0309048.pdf

- Towards an actual implementation: https://people.idsia.ch/~juergen/selfreflection.pdf
