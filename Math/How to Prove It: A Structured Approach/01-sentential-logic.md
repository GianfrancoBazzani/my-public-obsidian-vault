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

## 1.2 Truth Tables

When we evaluate the truth or falsity of a statement, we assign to it one of the labels **true** or **false**, and this label is called its **truth value**. For a set of statements we can summarize all the possibilities of their truth values in a table. This is called a truth table.

Each row of the truth table represents one possible combination of truth values for the statements.

For example, this is the truth table of the conjunction $P \land Q$:

| $P$ | $Q$ | $P \land Q$ |
| --- | --- | ----------- |
| T   | T   | T           |
| T   | F   | F           |
| F   | T   | F           |
| F   | F   | F           |

The truth table for $P \lor Q$ is a little trickier. Should $P \lor Q$ be true or false in the case in which $P$ and $Q$ are both true? Does $P \lor Q$ mean "$P$ or $Q$, or both" or does it mean "$P$ or $Q$, but not both"? The first way of interpreting the word or is called the **inclusive** or, and the second is called the **exclusive** or. In mathematics, or always means inclusive or, unless specified otherwise, so we will interpret $\lor$ as inclusive or.

This is the truth table of the disjunction $P \lor Q$:

| $P$ | $Q$ | $P \lor Q$ |
| --- | --- | ---------- |
| T   | T   | T          |
| T   | F   | T          |
| F   | T   | T          |
| F   | F   | F          |

A way of making truth tables more compactly. Instead of using separate columns to list the truth values of the component parts of a formula, just list those truth values below the corresponding connective symbol in the original formula.

For example, this is the compact truth table of $\neg(P \lor \neg Q)$. The column below $\neg Q$ shows the negation of $Q$, the column below $\lor$ shows $P \lor \neg Q$, and the column below the first $\neg$ shows the truth value of the whole formula:

| $P$ | $Q$ |     | $\neg$ | $(P$ | $\lor$ | $\neg$ | $Q)$ |
| --- | --- | --- | ------ | ---- | ------ | ------ | ---- |
| T   | T   |     | F      | T    | T      | F      | T    |
| T   | F   |     | F      | T    | T      | T      | F    |
| F   | T   |     | T      | F    | F      | F      | T    |
| F   | F   |     | F      | F    | T      | T      | F    |

Truth tables can be used for the analysis of the validity of arguments. We need to represent in the truth table the premises and the conclusion of the argument. Recall that an argument is valid if the premises cannot all be true without the conclusion being true as well.

**Example 1.2.3.1** Consider the following argument. Either John isn't smart and he is lucky, or he's smart. John is smart. Therefore, John isn't lucky. We let $S$ stand for "John is smart" and $L$ stand for "John is lucky". Then the argument has the form:

$$
\begin{array}{l}
(\neg S \land L) \lor S \\
S \\
\hline
\therefore \neg L
\end{array}
$$

> [!NOTE]
> The symbol $\therefore$ means "therefore".

If we build the truth table of this argument for both premises and the conclusion

| $S$ | $L$ |     | $(\neg$ | $S$ | $\land$ | $L)$ | $\lor$ | $S$ |     | $S$   |     | Conclusion ($\neg L$) |
| --- | --- | --- | ------- | --- | ------- | ---- | ------ | --- | --- | ----- | --- | --------------------- |
| F   | F   |     | T       | F   | F       | F    | **F**  | F   |     | **F** |     | T                     |
| F   | T   |     | T       | F   | T       | T    | **T**  | F   |     | **F** |     | F                     |
| T   | F   |     | F       | T   | F       | F    | **T**  | T   |     | **T** |     | T                     |
| T   | T   |     | F       | T   | F       | T    | **T**  | T   |     | **T** |     | F                     |

Both premises are true in lines three and four of this table. The conclusion is also true in line three, but it is false in line four. Thus, it is possible for both premises to be true and the conclusion false, so the argument is invalid. In fact, the table shows us exactly why the argument is invalid. The problem occurs in the fourth line of the table, in which $S$ and $L$ are both true (John is both smart and lucky). Thus, if John is both smart and lucky, then both premises will be true but the conclusion will be false, so it would be a mistake to infer that the conclusion must be true from the assumption that the premises are true. From the two premises, it clearly doesn't follow that John is not lucky, because he might be both smart and lucky.

Notice here that the truth table of the formula $(\neg S \land L) \lor S$ is exactly the same as the truth table for the simpler formula $L \lor S$. Because of this, we say that the formulas $(\neg S \land L) \lor S$ and $L \lor S$ are **equivalent**. Equivalent formulas always have the same truth value no matter what statements the letters in them stand for and no matter what the truth values of those statements are.

**Example 1.2.3.2** Let $B$ stand for the statement "The butler is innocent," $C$ for the statement "The cook is innocent," and $L$ for the statement "The butler is lying." Then the argument has the form:

$$
\begin{array}{l}
\neg ( B \land C)\\
L \lor C \\
\hline
\therefore L \lor \neg B
\end{array}
$$

If we build the truth table of this argument for both premises and the conclusion:

| $B$ | $C$ | $L$ |     | $\neg$ | $(B$ | $\land$ | $C)$ |     | $L$ | $\lor$ | $C$ |     | Conclusion ($L \lor \neg B$) |
| --- | --- | --- | --- | ------ | ---- | ------- | ---- | --- | --- | ------ | --- | --- | ---------------------------- |
| F   | F   | F   |     | **T**  | F    | F       | F    |     | F   | **F**  | F   |     | T                            |
| F   | F   | T   |     | **T**  | F    | F       | F    |     | T   | **T**  | F   |     | T                            |
| F   | T   | F   |     | **T**  | F    | F       | T    |     | F   | **T**  | T   |     | T                            |
| F   | T   | T   |     | **T**  | F    | F       | T    |     | T   | **T**  | T   |     | T                            |
| T   | F   | F   |     | **T**  | T    | F       | F    |     | F   | **F**  | F   |     | F                            |
| T   | F   | T   |     | **T**  | T    | F       | F    |     | T   | **T**  | F   |     | T                            |
| T   | T   | F   |     | **F**  | T    | T       | T    |     | F   | **T**  | T   |     | F                            |
| T   | T   | T   |     | **F**  | T    | T       | T    |     | T   | **T**  | T   |     | T                            |

Both premises are true in lines two, three, four, and six of this table, and the conclusion is also true in each of those lines. Thus, it is not possible for both premises to be true and the conclusion false, so the argument is valid.


### Logical Equivalences

**De Morgan's laws**

$$\neg(P \land Q) \equiv \neg P \lor \neg Q$$
$$\neg(P \lor Q) \equiv \neg P \land \neg Q$$

**Commutative laws**

$$P \land Q \equiv Q \land P$$
$$P \lor Q \equiv Q \lor P$$

**Associative laws**

$$P \land (Q \land R) \equiv (P \land Q) \land R$$
$$P \lor (Q \lor R) \equiv (P \lor Q) \lor R$$

**Idempotent laws**

$$P \land P \equiv P$$
$$P \lor P \equiv P$$

**Distributive laws**

$$P \land (Q \lor R) \equiv (P \land Q) \lor (P \land R)$$
$$P \lor (Q \land R) \equiv (P \lor Q) \land (P \lor R)$$

**Absorption laws**

$$P \lor (P \land Q) \equiv P$$
$$P \land (P \lor Q) \equiv P$$

**Double negation law**

$$\neg\neg P \equiv P$$

Many of the equivalences in the list should remind you of similar rules involving +, *, and - in algebra. As in algebra, these rules can be applied to more complex formulas, and they can be combined to work out more complicated equivalences. Any of the letters in these equivalences can be replaced by more complicated formulas, and the resulting equivalence will still be true.

### Tautology and Contradictions

Formulas that are always true, such as $P \lor \neg P$, are called **tautologies**. Similarly, formulas that are always false are called **contradictions**. For example, $P \land \neg P$ is a contradiction.

**Example 1.2.6** Are these formulas tautologies, contradictions, or neither?

a)
$$P \lor (Q \lor \neg P)$$

We can simplify this formula to:

$$P \lor \neg P \lor Q$$

where $P \lor \neg P$ is a tautology as it always evaluates to true, then the entire formula is also a tautology as $True \lor Q$ always evaluates to true.

b)
$$P \land \neg (Q \lor \neg Q)$$

$Q \lor \neg Q$ is a tautology as it always evaluates to true, so the negation always evaluates to false. So the whole formula is a contradiction as it always evaluates to false.

c) 
$$P \lor \neg (Q \lor \neg Q)$$

$Q \lor \neg Q$ is a tautology as it always evaluates to true, so the negation always evaluates to false. The formula can be simplified to $P \lor False$, which always evaluates to $P$. Thus, the formula is neither a tautology nor a contradiction.


We can also draw the truth table for the three formulas:

| $P$ | $Q$ |     | $P \lor (Q \lor \neg P)$ |     | $P \land \neg (Q \lor \neg Q)$ |     | $P \lor \neg (Q \lor \neg Q)$ |
| --- | --- | --- | ------------------------ | --- | ------------------------------ | --- | ----------------------------- |
| F   | F   |     | T                        |     | F                              |     | F                             |
| F   | T   |     | T                        |     | F                              |     | F                             |
| T   | F   |     | T                        |     | F                              |     | T                             |
| T   | T   |     | T                        |     | F                              |     | T                             |

The table confirms the analysis: the first formula is always true (a tautology), the second formula is always false (a contradiction), and the third formula has the same truth values as $P$ (neither).


We can now state a few more useful laws involving tautologies and contradictions.

**Tautology laws**

$$P \land (\text{a tautology}) \equiv P$$
$$P \lor (\text{a tautology}) \text{ is a tautology}$$
$$\neg(\text{a tautology}) \text{ is a contradiction}$$


**Contradiction laws**

$$P \land (\text{a contradiction}) \text{ is a contradiction}$$
$$P \lor (\text{a contradiction}) \equiv P$$
$$\neg(\text{a contradiction}) \text{ is a tautology}$$