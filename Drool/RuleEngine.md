## Rule Engine ##

Drool is a Rule Engine that uses rule-based approach to implement a Production Rule System.  

Production Rule System is a representation of propositional and first-order logic. Production Rule System's brain is Inference Engine which filters out facts and match against the Production Rule (Pattern Matching) to infer conclusion.

The Inference Engine of Drool uses Rete algorithm to implement Pattern Matching. 

Rules are stored in Production Memory and facts are stored in Working Memory. The Inference Engine executes Pattern Matching process by matching the facts against rules.   

If conflict occurs during Pattern Matching, Agenda will resolve the conflicts by Conflict Resolution strategy. 

[Rule Engine](https://docs.jboss.org/drools/release/5.3.0.Final/drools-expert-docs/html/ch01.html)
