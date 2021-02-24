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
