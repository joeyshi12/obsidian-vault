# JavaScript
JavaScript is a is a *non-blocking*, *asyncronous*, *single-threaded*, *concurrent* language with an *event-loop*

## Single-threaded
JavaScript can only have one sequence of instruction execution occurring over time, which are managed by the event-loop.
The set of instructions to be executed are pushed and popped from the call stack whenever a function is called and completed.

## Event-loop
Async functions with a callback are handled by *webapis*.
Once a webapi call is complete, the callback function call is pushed onto the *task queue*.
The *event loop* constantly checks if the stack is empty.
When the stack is empty, an item from the *task queue* is pushed onto the stack.

| Step 1                                    | Step 2                                    | Step 3                                          |
| ----------------------------------------- | ----------------------------------------- | ----------------------------------------- |
| ![[Pasted image 20220508145533.png\|300]] | ![[Pasted image 20220508145511.png\|300]] | ![[Pasted image 20220508145557.png\|300]] |



