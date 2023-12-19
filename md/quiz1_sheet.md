- The agent function maps from percept histories to actions
- For each possible percept sequence, a rational agent should select an action that is expected to maximize its performance measure, given the
evidence provided by the percept sequence and whatever built-in knowledge the agent has.
- Agents can perform actions in order to modify future percepts so as to obtain useful information (information gathering, exploration)
- An agent is autonomous if its behavior is determined by its own experience (with ability to learn and adapt)
- PEAS: Performance measure, Environment, Actuators, Sensors

Task Environments & their properties

- Fully vs. partially observable vs. unobservable
- Single vs. multi-agent
- Competitive vs. cooperative & partially cooperative (partially competitive)
- Deterministic vs. non-deterministic vs. stochastic
- Episodic vs. Sequential
- Static vs. Dynamic
- Discrete vs. continuous
- Known vs. unknown

### Different types of Agents
- <span class="underline">Simple reflex agent</span>: These agents select actions on the basis of the current percept, ignoring the rest of the percept history. These agents work only when the environment is fully observable.

- <span class="underline">Model-based reflex agent</span>:  The knowledge about "how the world works" — whether implemented in simple Boolean circuits or in complete scientific theories — is called a model of the world. This agent uses a state which is a function of current state, action, percept and rules. It uses this state to decide the next action.

- <span class="underline">Goal-based agent</span>: It keeps track of the world state as well as a set of goals it is trying to achieve, and chooses an action that will (eventually) lead to the achievement of its goals.

- <span class="underline">Utility-based agent</span>:  It uses a model of the world, along with a utility function that measures its preferences among states of the world. Then it chooses the action that leads to the best expected utility, where expected utility is computed by averaging over all possible outcome states, weighted by the probability of the outcome.

- <span class="underline"> General Learning Agent</span>: A learning agent can be divided into four conceptual components
    - **learning element**, which is responsible for making improvements
    - **performance element**, which is responsible for selecting external actions. The performance element is what we have previously considered
to be the entire agent: it takes in percepts and decides on actions.
    -  The learning element uses feedback from the **critic** on how the agent is doing and determines how the performance element should be modified to do better in the future.
    - **Problem generator**,  It is responsible for suggesting actions that will lead to new and informative experiences.

## Ways to represent states and transition between them
- **Atomic representation**: a state (such as B or C) is a black box with no internal structure.
- **Factored representation**: a state consists of a vector of attribute values; values can be Boolean, realvalued, or one of a fixed set of symbols.
- **Structured representation**: a state includes objects, each of which may have attributes of its own as well as relationships to other objects. 


### Logic
- Well formed formula (wff): An atomic proposition is a wff
- Logical inference is used to create new sentences that logically follow from a given set of propositional logic sentences (Knowledge Base,KB).
- sound - inference rule does not create any contradictions
- complete - inference rule is able to produce every expression that logically follows from (is entailed by) the KB.

Interpretation for propositional logic is a mapping assigning a truth value to each of the simple sentences of the language.    

- Satisfiability: We say that an interpretation $i$ satisfies a sentence $\iff$ it is true under that interpretation
- Validity: A sentence is valid $\iff$ it is satisfied by every interpretation.
- Unsatisfiability: $\iff$ it is not satisfied by any interpretation

We would like to know that given some sentences, whether other sentences are or are not logical conclusions. This relative property is known  as logical entailment. Formally, a set of sentences $\Delta$ logically entails a sentence $\varphi$ (written $\Delta \vDash \varphi$)
if and only if every interpretation that satisfies $\Delta$ also satisfies $\varphi$. For
example, the set of sentences $\{p, p \lor \, q\}$ logically entails the sentence $(q)$.

### CNF Form
- Eliminate $\iff$, replacing $\alpha \iff \beta$ with $(\alpha \rightarrow \beta) \land (\beta \rightarrow \alpha)$.
-  Eliminate $\rightarrow$, replacing $\alpha \rightarrow \beta$ with $\neg \alpha \lor \beta$
- Requires $\neg$ to appear only in literals, so we "move $\neg$ inwards" i.e. distribute it in a bracket.
- Distribute $\lor$ over $\land$, so final looks like $(\alpha \lor \beta) \land (\alpha \lor \gamma) \iff (\alpha \lor (\beta \land \gamma))$

To show that $KB \vDash \alpha$, we show that $(KB \land \neg\alpha)$ is unsatisfiable


- CNFSentence → $Clause_1 \land \dots \land Clause_n$
- Clause → $Literal-1 \land \dots \land Literal_m$
- Literal → $Symbol | \neg Symbol$
- Symbol → $P | Q | R | \dots $
- DefiniteClauseForm → $(Symbol_1 \land \dots \land Symbol_l) \rightarrow Symbol$
- GoalClauseForm → $(Symbol_1 \land \dots \land Symbol_l) \rightarrow False$
- HornClauseForm → $DefiniteClauseForm | GoalClauseForm$

Read forward chaining and backward chaining 
