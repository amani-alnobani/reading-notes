# React: Component Lifecycle Events
## What are component lifecycle events?
#### React lets you define components as classes or functions. The methods that you are able to use on these are called lifecycle events. These methods can be called during the lifecycle of a component, and they allow you to update the UI and application states.
![](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp)
## Mounting
#### When an instance of a component is being created and inserted into the DOM it occurs during the mounting phase. Constructor, static getDerivedStateFromProps, render, componentDidMount, and UNSAFE_componentWillMount all occur in this order during mounting.
## Updating
#### Anytime a component is updated or state changes then it is rerendered. These lifecycle events happen during updating in this order.
#### static getDerivedStateFromProps, shouldComponentUpdate, render, getSnapshotBeforeUpdate, componentDidUpdate, UNSAFE_componentWillUpdate, UNSAFE_componentWillReceiveProps
## Unmounting
#### The final phase of the lifecycle if called when a component is being removed from the DOM. componentWillUnmount is the only lifecycle event during this phase.
## UNSAFE Lifecycle Events
![](https://miro.medium.com/max/778/1*4y9V5936WdJKaIeVPFEa3w.png)
## Handling Events
### Handling events with React elements is very similar to handling events on DOM elements. There are some syntax differences:
1. React events are named using camelCase, rather than lowercase.
2. With JSX you pass a function as the event handler, rather than a string.