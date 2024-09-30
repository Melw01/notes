# Practical Guidelines About State

- Use a state variable for any data that the component should keep track of ("remember") over time. **This is data that will change at some point**. In Vanilla JS, that's a let variable, or an [] or {}
- Whenever you want something in the component to be **dynamic**, create a piece of state related to that "thing", and update the state when the "thing" should change (aka "be dynamic")
- If you want to change the way a component looks, or the data it displays, **update its state**. This usually happens in an **event handler** function.
- When building a component, imagine its view as a **reflection of state changing over time.**
- For data that should not trigger component re-renders, _don't use state_. Use a regular variable instead. This is a common beginner mistake.

# State vs. Props

- State
  - **Internal** data, owned by component
  - Component "memory"
  - Can be updated by the compoennt itself
  - Updating state causes component to re-render
  - Used to make components interactive
- Props
  - **External** data, owned by parent component
  - Similar to function parameters
  - Read-only
  - **Receiving new props causes component to re-render.** Usually when the parent's state has been updated
  - Used by parent to configure child component ("settings")
