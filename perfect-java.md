# Perfect Java: What if developers never made mistakes?

What would a bare-minimum version of Java (including its environment) look like if

- all developers knew everything there is to know about the language
- human errors were removed from the equation
- all developers knew everything about their own system and the functional requirements

Requirements:

- Must still be object-oriented (objects with methods)

## Dynamic typing

Developers can take care of their types on their own, thank you very much.

- primitives
- Objects
- __interfaces__ (only abstract classes - but no `abstract`)

`var`? Make everything an object?

## Almost no modifiers

There would be no need for most modifiers on variables, methods, or classes:

- `private`
- `protected`
- `public`


- Everything could be public
- No `final`: developers would never overwrite this.
- No `abstract`: developers would never instantiate a class that is not meant to be instantiated.

`static` would still be required, though, as it serves an actual purpose.

## No immutable state

Why force immutable state upon a developer who will never abuse the system (and thus, never lose performance)?

- fixed-size lists

## No Exceptions

- At least no `checked` exceptions.
- Even though some developers throw Exceptions as a "pattern", a better solution is to use monads from functional programming like `Try` or `Either`, which already exist to some extent.

## No style checking

Developers who don't make mistakes also don't introduce technical debt. This removes the need for libraries like

- [`modernizer-maven-plugin`](https://github.com/andrewgaul/modernizer-maven-plugin)
- [`pmd`](https://pmd.github.io/)

## No refactoring

Nope, except if the requirements change. No payment of technical debt.

## No unit/integration/system/e2e/acceptance/qa tests

Goodbye,

- Spock
- JUnit
- TestNG
- Hamcrest (and other matchers)
- Every framework-specific test

## No task/issue tracking or bug report system

Nope

## No memory leaks

Duh.

## No maintenance projects; only features

Of course there would be no need for bug fixing, uptime maintenance, or the like. The only exception is server maintenance.

## No build tools?

All developers are familiar with the classpath, completely removing the need for a build tool: one could simply use the same command/script for all projects, as standardisation is to be expected if all developers code in exactly the same way.

## No different libraries solving the same problems

Except for
- functional/imperative solutions
- embedded/standalone servers
- a few other things

## Complete keyword rundown (46 + 3 literals = 49)

- <del>`abstract`</del>
- <del>`assert`</del>
- <del>`boolean`</del>
- ? `break`
- <del>`byte`</del>
- <del>`case`</del> (no need for this AND if-else)
- <del>`catch`</del>
- <del>`char`</del>
- `class`
- <del>`const`</del> (already not used)
- `continue`
- <del>`default`</del> (with no interfaces and no switches that don't cover everything)
- `do`
- <del>`double`</del>
- `else`
- ? `enum` (is there really any need for this wrapper around classes with static fields?)
- `extends`
- <del>`final`</del>
- <del>`finally`</del> (no exceptions)
- <del>`float`</del>
- `for`
- <del>`goto`</del>
- `if`
- <del>`implements`</del> (no interfaces)
- `import`
- <del>`instanceof`</del> (no need, we already know: dynamic typing)
- <del>`int`</del>
- <del>`interface`</del>
- <del>`long`</del>
- `native`
- <del>`private`</del>
- <del>`protected`</del>
- <del>`public`</del>
- ? `return` (the final evaluation could always be returned, see Ruby)
- <del>`strictfp`</del> (no need, good developers don't use floats in this way
- `super`
- `switch`
- ? `synchronized`
- `this`
- <del>`throw`</del> (no exceptions, just return an `Either` or something)
- <del>`throws`</del> (no checked exceptions)
- `transient`
- <del>`try`</del> (no exceptions)
- <del>`void`</del> (just don't put anything, expicitness is not important when no one makes mistakes)
- ? `volatile`
- `while`

(enter literal values)

- <del>`false`</del> (no need for explicit statement of boolean values, see Haskell)
- <del>`null`</del> (Optional is less error-prone)
- <del>`true`</del> (no need)

### That leaves us with

Definitely 14:

- `class`
- `continue`
- `do`
- `else`
- `extends`
- `for`
- `if`
- `import`
- `native`
- `super`
- `switch`
- `this`
- `transient`
- `while`

Maybe 5:

- `break`
- `enum`
- `return`
- `synchronized`
- `volatile`

