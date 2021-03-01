# React

### Functional approach

##### `useEffect`
- rendered first and scheduled to run in next tick.
- second argument:
  - *none*: behaves like `componentDidUpdate`
  - *[]*: behaves like `componentDidMount`
  - *array of values*: list of dependent values
- returned function behaves like `componentDidUnmount`

##### `useState`
- the state value setter function is asynchronous is nature. If we set the state and we close a scope upon the state, there is a chance that a closure is formed before even the value of state is updated. It will reflect the previous value.

##### `useRef`
- instead of using instance variable in class components, we can use `useRef`
- gives object with only `current` key .i.e. object is sealed.

##### `useContext`
##### `useReducer`
##### `useMemo`
- when parent re-renders, it cascades to all its children
- you give it a function of how to compute something and then you give its dependencies and it will only re-compute when its dependencies changes.

##### `useCallback`
- *memo*: unless none of my properties have changed, don't re-render me

##### `useLayoutEffect`
- calls render method twice but paints only once
- synchronous with render unlike useEffect

##### `useImperativeHandle`
- child control parent

##### `forwardRef`
