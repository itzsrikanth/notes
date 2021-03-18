# Functional-Light-JS

### Intro
- Ground-up approach
- `fp` in isolation is not possible
- pros:
  - relatively declarative
  - readability
  - maintainence
  - provable - math-based, testable
- cons:
  - not performant
  - not familiar, convienient

#### Topics
- functions
- closure
- composition
- immutability
- recursion
- lists/data structures
- async
- FP lib

### Function purity
- qualification for a `function` is to return an output, unless it is called a `procedure` from procedural programming
- `functions` can call only other `functions`, if they call `procedures`, they are also termed as a `procedure`
- `function` is a semantic relation b/w input and output
- side-effects:
  - indirect input
  - indirect output
  - no access or assignment outside
  - e.g:
    - console.log / IO
    - db storage
    - network calls
    - timestamp
    - DOM
    - random numbers
    - cpu heat, cpu time delay
    - global variables
- function call matters more than function, to distinguish it b/w function & procedure
- `constants`: variables which holds constant value without facing re-assignment, do not contribute to side-effects, it is still a `pure function`
- question of function being pure is not having binary answer, depends on level of confidence of reader on the code

#### Converting to pure function using adapter function
1. save the current state
2. setup initial state
3. call the side effect
4. capture new state
5. restore old state
6. return captured state

### Argument adapters
- function definition has `parameters`
- original value passed during function call is called `arguments`
- `shape of function`: number/count and type of input and output in function
- `unary` function: function with single i/p & single o/p
- `binary` function
- `enary` function
- `HoF` (higher order function): either receives one/more function(s) OR returns one/more function(s) 
- main functionality of adapter functions is to generate a function which has got a shape expected in code by doing some transformations under the hood, necessary to match the shape

### Point Free
- making functions with other functions
- equational reasoning
- relation between functions implicitly clear
- `composition`: one function's output becomes input for another function

### Closure
#### Lazy vs eager
- whenever a code is called up very rarely, we can put it inside function and defer the logic unless it is invoked explicitly
- but we can do eager by calling it outside nested function. this caches it and we need not re-execute it repeatedly

#### memoization
- in order to achieve both lazy and eager execution benefit, we end up closing over a variable outside a scope. Thereby creating an impure function
- if the output remains same, we can be convinced that it is pure, with low degree of confidence

#### Pure function:
Definition evolution for pure function
1. take input, return output
2. relation b/w input and output
3. direct inputs and outputs
4. can be indirect input as long as not changing
5. everytime i call function with same input, same output should be produced
6. `referential transparency`: if a function call can be replace with its return value and it does not affect any other part of program. `Haskell` has inbuilt guarantee for that in compiler level

#### Currying applications
- When we have a function, say, `ajax` call, it may have 3 args
- the order of args should be general -> specific
- this way, a minimum (specialized) arguments will be passed to semantically named function
- if we want to increase degree of specialization, more currying can be done
- this produces relations between each of the function
- it keeps all the functions unary
- types:
  - loose currying
  - string currying

#### Composition
- composition of non-unary functions can be achieved by currying

### Immutability
- change should be there, but predictable
- types:
  - assignment immutability
- in general functional programming, re-assignment itself is not a preferred action. so there is a need for `const` keyword in language?
- passing up a value to a function not defined in the scope is dangerous since it can be source of bug by introducing unexpected changes. Functional programmers try to avoid such source of errors by using design patterns
- when you need a mutable data structure, what you actually need is immutable data structure. It allows structured, controlled intentional mutation

### Lists
#### Functors
- a value/collection over which values in it can be mapped
- transformation operation


### Glossary
- `predicate` - in general, unary functions returning true or false
