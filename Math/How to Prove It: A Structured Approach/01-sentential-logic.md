# Sentential Logic

> **Sentential** (adjective): of or related to a sentence. In logic, sentential logic (also called propositional logic) studies whole sentences and the logical connectives that combine them, not the internal structure of the sentences.

## 1.1 Deductive Reasoning and Logical Connectives

Deductive reasoning is the foundation on which proofs are based. We arrive at a **conclusion** from the assumption that some other statements, called **premises**, are true.

We will say that an argument is valid if the premises cannot all be true without the conclusion being true as well.

If an argument has the form:

- $P$ or $Q$.
- Not $Q$.
- Therefore, $P$.

It is this form, and not the subject matter, that makes this argument valid. Replacing certain statements in each argument with letters has two advantages. First, it keeps us from being distracted by aspects of the arguments that don't affect their validity. Second, you can tell that this argument form is valid without even knowing what $P$ and $Q$ stand for.

In most deductive reasoning, and in particular in mathematical reasoning, the meanings of just a few words give us the key to understanding what makes a piece of reasoning valid or invalid.

**Connective symbols** stand for some of the words used to combine statements. The first three connective symbols to introduce, and the words they stand for, are:

| Symbol | Word | Name        |
| ------ | ---- | ----------- |
| ∨      | or   | disjunction |
| ∧      | and  | conjunction |
| ¬      | not  | negation    |

Thus, if $P$ and $Q$ stand for two statements, then we will write $P \lor Q$ to stand for the statement "$P$ or $Q$", $P \land Q$ for "$P$ and $Q$", and $\neg P$ for "not $P$" or "$P$ is false".

The symbols ∧ and ∨ can only be used between two statements, to form their conjunction or disjunction, and the symbol ¬ can only be used before a statement, to negate it. This means that certain strings of letters and symbols are simply meaningless. For example, P ¬ ∧ Q, P ∧ ∨ Q and P ¬ are all "ungrammatical" expressions in the language of logic. "Grammatical" expressions are sometimes called **well-formed** formulas or just **formulas**.

### Exercises

5) Which of the following expressions are well-formed formulas?

   a) $\neg(\neg P \lor \neg\neg R)$ — ✅ Well-formed formula.

   b) $\neg(P, Q, \land R)$ — ❌ Invalid formula.

   c) $P \land \neg P$ — ✅ Well-formed formula.
   
   d) $(P \land Q)(P \lor R)$ — ❌ Invalid formula.

6) Identify the premises and conclusions of the following deductive arguments and analyze their logical forms. Do you think the reasoning is valid?

    a) Jane and Pete won't both win the math prize. Pete will win either the math prize or the chemistry prize. Jane will win the math prize. Therefore, Pete will win the chemistry prize.
    
    <u>**Premises**</u>

    $\neg(J_m \land P_m)$

    $P_m \lor P_c$

    $J_m$

    <u>**Conclusion**</u>

    Pete will win the chemistry prize. $P_c$

    The reasoning is valid, and the conclusion holds true. Jane won the math prize, which implies that Pete did not. So if Pete did not win the math prize, he won the chemistry prize.
    
    b) The main course will be either beef or fish. The vegetable will be either peas or corn. We will not have both fish as a main course and corn as a vegetable. Therefore, we will not have both beef as a main course and peas as a vegetable.

    <u>**Premises**</u>

    $B \lor F$

    $P \lor C$

    $\neg (F \land C)$

    <u>**Conclusion**</u>

    We will not have both beef as a main course and peas as a vegetable. $\neg (B \land P)$
    
    The reasoning is invalid and the conclusion does not hold, as none of the premises enforces that if we have beef as a main course we cannot have peas as a vegetable, we can have either peas or corn.

    c) Either John or Bill is telling the truth. Either Sam or Bill is lying. Therefore, either John is telling the truth or Sam is lying.

    <u>**Premises**</u>
    
    $J \lor B$
    
    $\neg S \lor \neg B$

    <u>**Conclusion**</u>

    $J \lor \neg S$

    Either John is telling the truth or Sam is lying $J \lor \neg S$
    
    The reasoning is valid, and the conclusion holds true as if John tells the truth it means that Bill is lying, and if Bill lies Sam cannot lie.

    d) Either sales will go up and teh boss will be happy, or expenses will go up and the boss won't be happy. Therefore, sales and expenses will not both go up.

    <u>**Premises**</u>
    
    $(S \land B) \lor (E \land \neg B)$

    <u>**Conclusion**</u>
    
    Sales and expenses will not both go up $\neg (S \land E)$ 
    
    The reasoning is invalid and the conclusion does not hold, as the premises allow both sales and expenses to go up, they only constrain whether the boss is happy or not in that situation.
