# Deep JS
*Kyle Simpson*

### Scopes 
1. `functions` in Javascript are first class citizens. It means, they can be passed around in code as variables. This is possible only because of `closures` which closes over the variables of the lexical scopes above it. These three are pillars of the building.

2. The are more than one pass in JS compilation. Multiple partial JIT compilations/optimizations are done. It even throws syntax error without running all lines. So, it is a compiled language. Only difference is the distribution model where in other languages the `exe` is built and sent but here source code itself is sent.

3. During the first pass of the program, the scoping is set.
   - Individual unit of scope is function

4. compiler & scope/bucket-manager (having conversation)
   - formal variable/function declaration are checked for existance
   - say, compiler asks global scope manager if it has a variable/function with `xyz` name, if not then scope-manager adds it. we need not be concerned on its value for now.
   - when function declaration is identified, recursively new bucket/scope is created
   - if any informal declarations are found, it is skipped for later stage.
  
5. execution (JVM & scope-manager conversation):
   - keywords like `var` are removed during compilation
   - store `metadata` about variable that if it is `lvalue` or `rvalue`
   - Javascript Virtual Manager (JVM) takes over and talks to scope-manager.
   - when we do not have a variable in current scope which was skipped in compilation,
     - scope-manager goes a scope above recursively till global scope
     - if not found, global scope creates one at run-time (implicitly -- `lvalue` only)
     - it is `ReferenceError` in `strict` mode. it is undeclared, not `undefined`.

6. shadowing: two different variable/function in different scope with same name. Once we shadow in compile time, we cannot lexically access upper scope's value if shadowed.
7. Strict mode does not allow implicit global variables because it is slower to create a variable at runtime than have to modify an existing lexical scope as opposed to being able to figure it out at compile time. in general, it will be hard to optimize code.
8. Every single JS file is a separate program, sharing same global scope.
9. Unfulfilled LHS reference can create global values but unfulfilled RHS will cause `ReferenceError`.
10. lexical scope is fixed / static. It happens that when a compiler finds variable, it registers its scope along with it. so, it need not lookup it every time during runtime.
11. Function expressions are not added to its enclosing scope, bcz their name identifier processing are slightly reversed. name for `named function expression` will show up within its own scope. We will have self reference access to itself inside it.
12. `catch` control variable is only reported block scope
13. Named function expression advantage:
  - self-reference
  - debug
  - self-documenting
14. `lexical scope` are optimizable bcz we can predict at compile time, bcz the closures close over the values and takes them along wherever it is passed unlike in dynamic scope which needs to figured at runtime. becomes unpredictable as well as flexible.
15. Functions:
  - `SyntaxError` due to missing function name, when trying to invoke:
    ```javascript
      function(){}();
    ```
    This is because when parser encounters `function` keyword it treats it as `function declaration`, not as `function expression`. Adding parenthesis around it converts into a expression, bcz parens cannot contain statements.

    But then can be omitted when already function expression is expected like:
    ```javascript
    var i = function(){ return 10; }();
    true && function(){ /* code */ }();
    0, function(){ /* code */ }();
    ```

    So, in general, functions can be used as expressions without parens by prefixing with unary operators, this will save a byte:
    ```javascript
    !function(){ /* code */ }();
    ~function(){ /* code */ }();
    -function(){ /* code */ }();
    +function(){ /* code */ }();
    ```
    Or
    ```javascript
    new function(){ /* code */ }
    new function(){ /* code */ }()
    ```
  - `SyntaxError` due to missing expression:
    ```javascript
      function foo(){}();
    ```
    is equal to
    ```javascript
      function foo(){}
      ();
    ```
    Here, `()` is grouping operation with empty expression.
  - ```javascript
      function foo(){}(1);
    ```
    is equal to 
    ```javascript
      function foo(){}
      (1);
    ```
  - To recursively call self (anonymous function)
    ```javascript
    function() { arguments.callee(); };
    ```
16. `let` cannot replace `var`. Wherever we want to create temporary variable, use **Explicit blocks**:
  ```javascript
  {
    let tmp;
    tmp = a;
    a = b;
    b = tmp;
  }
  ```
  This pattern lets us restrict the scope of `tmp`
  - `for` loops' iterator should be declared as `let` because no reason for iterator to be available for use outside the `for` block.
  - find and replacing `var` with `let` losses the stylistic signal of the developer's intention. Some variables are intentional block scope and some are lexical, we will lose this info if all of them are replace entirely.
  - For readability, all the declarations of variables should be in the screen wherever it is going to get used. In case it is getting used after many lines, we can redeclare using `var` for variable scope understandability.
  - It would be sensible to use `const` with primitive datatypes
17. Hoisting
  - Function declaration vs expression: former gets hoisted
  - mutual recursion, circular dependency
  - Function hoisting is great, bcz declarations can be at bottom of file (even after return statement) and the execution can be at top so that we need to scroll till bottom to find them, but variable hoisting usage will confuse other people reading code.
  - Temporal Dead Zone (TDZ) error: 
  - `var`
    - variable is added at compile-time to its enclosing lexical scope
    - at runtime when scope starts, the variable gets initialized with `undefined` value
  - `let`
    - similar to `var`, it is added to lexical scope
    - but not initialized with `undefined` when scope begins, rather when it encounters the `let` line declaration. *Hence hoisting works with `let`, but does not gets initialized which causes the error*

### Closure
1. closure is ability of function to remember its lexical scope even when the funciton is executed outside the lexical scope.
2. examples:
  - settimeout, eventHandlers etc
  - ```javascript
    for (var i = 0; i < 5; i++) {
      setTimeout(function(){
        console.log(i);
      }, i * 100);
    }
    ```
    Here, 5 6s are printed bcz each `setTimeout` callback closes over same `var` declarations (attached to global/parent lexical scope). So, 6 is used in every closure.
    ```javascript
    for (let i = 0; i < 5; i++) {
      setTimeout(function(){
        console.log(i);
      }, i * 100);
    }
    ```
    But when `let` is used here, it creates a new variable for each `for` block and closure closes over individual copy of `i`.

    This can be again solved using IIFE by creating new lexical scopes and adding new `i` for each of them. Here, the `for` loop's `i` is shadowed
    ```javascript
    for (var i = 0; i < 5; i++) {
      (function(i){
        setTimeout(function(){
          console.log(i);
        }, i * 100)
      })(i);
    }
    ```

    Instead of lexical scope, we can do a block scoping by doing:
    ```javascript
    for (var i = 0; i < 5; i++) {
      let j = i;
      setTimeout(function(){
        console.log(j);
      }, j * 100);
    }
    ```
3. `closure` is not a `function`, it is its characteristics.
4. Module pattern: most imp code organisation pattern
   - an external scope, say function, in which this logic gets executed atleast once.
   - internal reference to publicAPI that we return from module, having closure over internal state
   - ES6, entire file content is treated as module with elements by default hidden.
5. Tips for efficient organisation in module:
   - Stateless functions are to be separted
   - DOM functions and data model functions to be separated


### Object oriented
1. dynamic scope -> this
  - pointing of `this` for a `this aware function` **only depends on how the function was called**
   - four ways of calling function:
      ```javascript
        var bar = 'bar1';
        function foo() {
          console.log(this.bar);
        }
      ```
      - *default binding rule*: not best way to call `this` aware function. when nothing match, points to global object in non-strict mode. but in strict mode, it is `undefined`
        ```javascript
          foo();    // "bar1"
        ```
      - implicit binding rule: call `foo` in context of `o2`. Here, we have a problem of `losing this-binding`. When `o2`'s `foo` is passed to somewhere else, that function will be called in different context and will lose `o2` as context.
        ```javascript
          var o2 = { bar: 'bar2', foo };
          o2.foo();   // "bar2"
        ```
      - explicit: `call` / `apply` <br />
        under the cover uses explicit hard-binding - `bind`
      - `new`: 
        - nothing to do with creating new instance of classes.
        - a poorly designed system to create new objects 
        - Four things happen when this is used:
          - brand new empty object created
          - **newly created object gets linked to another object**
          - newly created object in step-1 is passed as `this` context to the function
          - if the function does not return own object, `new` assumes that the object passed in should be returned i.e. "`return this;`"
        - any function with a `new` keyword infront is called `constructor call`
  - four rules for `this` precedence
    - if function called `new`, then use new created object
    - else if `call` or `apply` used? if yes, use that apply
    - called with context object
    - default: global (non-strict) or undefined (strict)
  - **A `new` keyword has power to trump hard-binding of `bind` method**
  - `this` is not special keyword in arrow function, just a regular variable.
2. Lexical scope give a author time predictability and `this` gives flexibility but hard-binding overshoots it. There is always a tension between them.
3. dont use `class` or `arrow function`
4. inheritance
5. behaviour delegation
6. OO vs OLOO (objects linked to other objects)

### Prototypes
1. Objects are built with `constructor calls` -- `new` keyword
2. A constructor makes an object ~~based on~~ "linked to" its own prototype. So, it is a `retroactive inheritance`. The prototype's properties are not copied to new ones, rather they are linked.

## Sources
- [IIFE - Benalman](http://benalman.com/news/2010/11/immediately-invoked-function-expression/)
