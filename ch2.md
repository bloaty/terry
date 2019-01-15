Chapter 2
=========

[dummy-preable]: # 'Install the Markdown+Math extension to render LaTeX expressions and make use of the global macros defined in the VSC workspace file, such as $\Succ$.'

**&#0167;&#8201;2.1.** We start with an empty universe of discourse. I guess we do have the empty set, but the objects we are going to introduce are not sets, so we will ignore it. Because there are no objects, we have nothing to denote by variables, and also no functions.

*Def.&#8201;2.1.1.* We only consider this "definition" insofar as it sets the goal of founding a mathematical object that behaves indistinguishably from $\mathbb{N}$. Most of the rest of &#0167;&#8201;2.1 is about devising a tractable set of axioms to define such an object.

*Axioms&#8201;2.1 & 2.2*. Our universe of discourse now contains some objects. In particular, we have $0$ and elements defined via applications of the successor function $\Succ{\fbox{?}}$. I think at this point we are justified in using variables $n$, $m$, etc., to denote an arbitrary element of $\mathbb{N}$ that is either $0$ or the successor of some element of $\mathbb{N}$. We have not yet claimed that there are distinct elements of $\mathbb{N}$ other than $0$ itself.

We can now speak of a formal language of math strings or expressions. This language so far consists of single variables (such as $n$, $m$), concrete elements of $\mathbb{N}$ (such $0$), and an arbitrary number of applications of the successor function to one of the above ($\Succ{(\Succ{n})}$, $\Succ{(\Succ{(\Succ{0})})}$, etc.). It feels reasonable to equate the statements "an expression $S$ is valid" and "$S$ denotes an object that exists."

In my naive semantics, I am going to distinguish *expressions* from *claims*.

Expressions are valid strings in my formal math language. An invalid string is not an expression. A string is invalid if no sequence of function applications will produce it from a valid string.

I consider functions strictly to be maps from valid strings to valid strings. All possible arguments to a function are valid strings, but not every function accepts every valid string. It is meaningless to apply a function to a string that cannot be demonstrated to be valid.

Expressions do not have truth values. They are meaningful insofar as they denote a specific object that exists (if the expression contains no variables) or an arbitrary object from among a collection of objects, all of which exist (if the expression does contain one or more variables).

For an expression that contains variables, we can consider the set of all valid simultaneous substitutions of concrete elements into the expression. We then then speak of the *extension* of the variables as the entire set of substitutions. The extension of the variable $n$ in the expression that's just $n$ by itself is all of $\mathbb{N}$. In a more complex expression, the choice of concrete substitutions for one of the variables may constrict the choice of substitutions for the others.

In particular, I can write an expression that denotes an arbitrary element of $\mathbb{N}$. I can also write an expression that denotes an element with more specific properties if I can prove that at least one concrete instance of such an object exists ("all $n$ that are the successor of a natural number").

I consider it invalid to try to select or express some $n$ if I cannot prove that an example of such exists ("an $n$ that is its own successor"). One way to show that no such $n$ exists is to demonstrate that the claim "$n$ exists" contradicts one of my axioms, directly or following some chain of argument. We would then conclude that $n$ is not an expression in our language and cannot participate in claims.

Claims have a truth value. Claims are either true or false. Claims either relate two (valid) expressions or two claims.

The only apparent relation over expressions so far is equality ($=$). Two expressions are equal if any valid, concrete, simultaneous substitution into the left-hand side is also a valid, concrete, simultaneous substitution into the right-hand side, and vice versa. If the two expressions are equal, the claim is true. It is otherwise false.

Suppose we demonstrate or axiomatically claim that there are natural numbers other than $0$. Then, the claim $0=0$ is true because $0$ is, trivially, the only conceivable value that can be substituted into the LHS and the RHS. The claim $n=n$ is true because $\mathbb{N}$ is the extension of both the RHS and the LHS. The claim $n=0$ is false, because the extension of the RHS is only $0$, while the extension of the LHS is $\mathbb{N}$. The claim "$n=0$ for all $n$ that are equal to $0$" is true, because the extension of the RHS and LHS is, once again, the same.

Immediately evident relations over claims are negation ($\neg$), conjunction ($\wedge$), disjunction ($\vee$), and implication ($\Rightarrow$).

It's not clear to me whether it is best to treat "$n=0\,\wedge\,n\neq0$" as, hypothetically, an expression which turns out to be an invalid string (because I can't demonstrate any such $n$). An alternative is to describe some formal mechanism that says that all instances of "n" in this claim represent "the same variable," and that for the compound claim to be true, the extension of $n$ wherever it appears must be the same. In that case, "$n=0\,\wedge\,n\neq0$" is false.

If $S$ and $T$ are claims, we call them equivalent if $S\,{\Rightarrow}\,T$ and $T\,{\Rightarrow}\,S$. We denote this by $S\,\Leftrightarrow\,T$, order unimportant.

Proving is the construction of a chain $S_1\,\Rightarrow\,S_2\,\Rightarrow\,S_3\,\Rightarrow\cdots$ where the first claim, the last claim, and every claim $S_i\,\Rightarrow\,S_{i+1}$ are true. Subsequent claims in the chain must be derived by the application of functions to the LHS and RHS of an equality claim. Because applying the same function to two expressions with the same extension should not change the extension of either the RHS or the LHS, we consider function application "truth-preserving."

Proving $\neg\,S$ "by contradiction" assumes that $S$ is true and derives $S\,\Rightarrow\,false$. Because we derived $false$ through function application and $true\,\Rightarrow\,false$ is false, it can only be the case that $\neg\,S$.