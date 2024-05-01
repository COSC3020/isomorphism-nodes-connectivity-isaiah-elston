# Isomorphism

Prove that if two graphs $A$ and $B$ have the same number of nodes and are completely connected, they must be isomorphic. I have started with the formal definition of isomorphism below. Add your answer to this markdown file. [This page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$G_1=(V_1 , E_1)$ is isomorphic to $G_2 = (V_2, E_2)$ if there exists a
one-to-one and onto function (bijection) $f: V_1 \rightarrow V_2$ such that $(u,v)
\in E_1$ iff $(f(u),f(v)) \in E_2$.

## Answer

Consider the following two graph templates:

$G_{1} = $

```mermaid
graph LR
A --- B 
B --- C
D --- C
A --- D
```

$G_{2} = $

```mermaid
graph BT
Z --- Y
Y --- X
Z --- W
W --- X
```

Once again, I am providing some example graphs solely for the benefit of the reader(s) to help them visualize the conditions that this proof is regarding. My reasoning below will be exclusively generalized and only reference $G_{1}$ or $G_{2}$ to be "templates" of any arbitrary graph that is completely connected **and** has an equivalent number of nodes as its pair graph. In other words, $G_{1}$ and $G_{2}$ are arbitrary graphs that satisfy the same conditions as the graphs depicted.

Suppose that $m$ is a mapping between any two arbitrary graphs $G_{1}$ and $G_{2}$. Moreover, suppose that $|N|$ represents the arbitrary *(yet equivalent)* number of nodes in a graph and that $|E|$ represents the arbitrary number of edges in a graph.

First and foremost, we must consider the relationship between edges and nodes in general. Since the graphs are assumed to be completely connected, we can make the generic claim that for any arbitrary number $|N|$ nodes, there **must** be exactly $|E| \equiv |N| - 1$ edges in the same graph. That claim follows from the very definition of *completely connected*. The completely connected property necessitates an edge to exist between any two **pairs** of nodes in a graph. The reason that we subtract one from the number of nodes is because completely connected does **not** implore each node to connect back to itself, hence there being one less edge than there are nodes.

In math notation, we can assert that the following property will always hold for any two graphs that are completely connected:

$$\begin{gather*}
|E| = (|N| - 1)
\end{gather*}
$$

Keeping that property in mind, we may now consider the requirements for two graphs to be isomorphic. In layman's terms, two graphs are isomorphic when there exists a bijective mapping between each edge **and** node of both graphs. In order to satisfy the definition of bijective, the mapping must be **both** surjective (onto) and injective (one-to-one). The property above is imperative to generalizing the presence of surjectivity and injectivity because by defining the number of edges in a graph in terms of the number of nodes, proving isomorphism becomes nigh trivial to do. Consider the following logic, and keep in mind that **it only follows for completely connected graphs**:

```math
\begin{gather*}
& |E| = (|N| - 1) && \text{\{The property from above\}} \\
\implies & (|E|_{G_{1}} \equiv |N|_{G_{1}} - 1) \wedge (|E|_{G_{2}} \equiv |N|_{G_{2}} - 1) \\ \\
& |N|_{G_{1}} \equiv |N|_{G_{2}} && \text{\{We assume the number of nodes in each graph is an equivalent value\}}\\
\implies & (|N|_{G_{1}}- 1) \equiv (|N|_{G_{2}} - 1) \\
\implies & |E|_{G_{1}} \equiv |E|_{G_{2}} && \text{\{The property from above\}} \\
\therefore & (|N|_{G_{1}} \equiv |N|_{G_{2}}) \Leftrightarrow (|E|_{G_{1}} \equiv |E|_{G_{2}}) && \text{*Assuming complete-connectivity} \\
&& \blacksquare
\end{gather*}
```

This proves that whenever we know the number of nodes ($|N|$) in two **completely connected** graphs to be equivalent, we can **always** contrive that the number of edges ($|E|$) will also be equivalent.

Finally, since we can now be sure that the number of nodes **and** the number of edges in any two completely connected graphs are equivalent, we have all the basis we need to guarantee isomorphism. That is, we now know that with precisely the same amount of nodes and edges in both graphs, there most definitely exists some mapping $m$ where every node and edge can **uniquely** map to a corresponding node and edge in the other graph. Moreover, since there are equivalent amounts of nodes and edges in each graph when $m$ uniquely maps each node and edge, nodes or edges cannot possibly be left out. 

In conclusion, when two graphs are completely connected and have the same number of nodes, we can simply apply a one-to-one mapping between them. After everything is mapped one-to-one, the onto property will follow naturally because there couldn't possibly be any additional nodes or edges unaccounted for in that particular scenario. We know that this holds true in general because the number and edges of nodes do not matter whatsoever so long as that number is the same between those two graphs. Therefore, since a bijective mapping between each node and edge is guaranteed to exist for any general case, we have proven that any two completely connected graphs with an equivalent number of nodes **must** be isomorphic to each other.
