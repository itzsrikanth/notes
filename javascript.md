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

## Sources
- [IIFE - Benalman](http://benalman.com/news/2010/11/immediately-invoked-function-expression/)
