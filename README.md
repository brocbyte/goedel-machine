## Gödel machines

Can we build it?

## Notes

- goedel machines - universal problem solvers = solver (environment) + proof-searcher (rewrite itself for good)

- p(1) - the initial software = e(1) + proof-search technique

- e(1) - the original policy for interacting with the environment (problem-solver)

### Proof searcher

- makes pairs (switchprog, proof) until it finds a proof of a "target theorem", which says:\
  _"the immediate rewrite of p through current program switchprog on the given machine implies higher utility than leaving p as is"_\
  ==> (we have global optimality from here)

- uses online extension of Universal Search (Levin search?)

- an axiomatic system A encoded in p(1):
  <ol type="a">
  <li> instruction semantics (hardware axioms) </li>
  <li> reward axioms </li>
  <li> environmant axioms </li>
  <li> uncertainty axioms; string manipulation </li>
  <li> initial state axioms </li>
  <li> the formal utility function u </li>
  </ol>

- ignores those self-improvements whose effectiveness it cannot prove

- target theorem:<br>
    > tt(s, t, switchprog) = [u(s, {wait_until(t), switchprog()}) > u(s, {scheduler})]

  or

  "is it useful to perform the switch at time t?"

- target theorem can be used in two ways:

  1. generate a candidate switchprog, run (time-bounded) + evaluate
  2. generate theorems from an axiomatic system, test them for equivalence with target theorem

- initial algorithm can be Hutter's HSEARCH


#### Instructions used by proof techniques

1. **get-axiom(n)** - appends n-th possible axiom to the current proof 
2. **apply-rule(k, m, n)** - applies the k-th inference rule to the m-th and n-th thrm in the current proof, appends result
3. **delete-theorem(m)** - deletes the m-th theorem in the currently stored proof
4. **set-switchprog(m, n)** - sets switchprog := s[m:n]
5. **check()** - tests whether the last theorem in proof is a target theorem
6. **state2theorem(m, n)** - creates a theorem of the form s\[m:n\](t1) = z, where t1 - a time measured after state2theorem was invoked

### Self-Reflective Systems



### Links

- Main page: https://people.idsia.ch/~juergen/goedelmachine.html

- Concept: https://arxiv.org/pdf/cs/0309048.pdf

- Towards an actual implementation: https://people.idsia.ch/~juergen/selfreflection.pdf
