# Section 7: Thinking in React: State Management

## The "Thinking in React" Process

1. Break the desired UI into **components** and establish the **component tree**.
2. Build a **static** version of React (without state)
3. Think about **state**:

- When to use state
- Types of state: local vs. global
- Where to place each piece of state

4. Establish **data flow**:

- One-way data flow
- Child-to-parent communication
- Accessing global state

> Note:
> Steps 3 and 4 are known as **"state management"**

## State Management

Deciding **when** to create pieces of state, what **types** of state are necessary, **where** to place each piece of state, and how data **flows** through the app

## Types of State:

1. Local State

- State needed **only by one or few components**
- State that is defined in a component and **only that component and child components** have access to it (by passing via props)
- We should always start with local state

2. Global State

- State that **many components** might need
- **Shared** state that is accessible to **every component** in the entire application
- We can define global state by using React's _Context API_ or an external global state management library _Redux_

## State: When and Where

```mermaid
graph TD;
    A[Need to store data]-->B[Will data change at some point?];
    B--Yes-->C[Can be computed from existing state/props?];
    C--Yes-->E[Derive State];
    B--No-->D[Regular const variable];
    C--No-->F[Should it re-render component?];
    F--Yes-->G[Place a new piece of state in component];
    F--No-->H[Ref];
    G-->I[Only used by this component?];
    I--Yes-->J[Leave in component];
    I--No-->K[Also used by a child component?];
    K--Yes-->L[Pass to child via props];
    K--No-->M[Used by one or a few sibling components?];
    M--Yes-->N[Lift state up to first common parent];
    M--No-->O[Probably global state];
```
