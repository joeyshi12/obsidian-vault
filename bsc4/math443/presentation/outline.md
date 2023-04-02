Motivation
-   Introduce flowgraphs

Flowgraphs are digraphs with a root.

what are dominators
- a good example of why dominators are important to compilers
- getting dominators is slow

That is, there is a vertex that has a path to every other vertex in the graph.
-   how this applies to control theory/compilers

Important for compiler design.
Consider single static assignment compilers.

The Result
-   There is a faster method using semidominators (define semidominators)
    -   also introduce: depth-first-search, preorder
-   Easy connection between semidominators and immediate dominators
-   Rough idea of how to find semidominators (can include proof, or slightly abstracted proof)
-   Intuitive argument of why it's faster (time complexity)

Visuals:
-   We can use the flowgraphs from our "First read of paper" to explain definitions and walk through algorithms
-   Additional visual: Correspondence between a program and flowgraph


Summary:

There is an O(m)