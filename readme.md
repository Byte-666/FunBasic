
FunBasic - Functional Basic
===========================

Let's create another basic dialect, this time let's turn Basic into an real FP language with all the goodies. Visual Basic from Microsoft is too enterprisey and boring and also very, very verbose, at least as verbose as Java because of the longer keywords.  
A Basic language must be basic, it should be simple, with only the minimum needed, basic as black, as they say. Incidentally I only wear black clothes without stamps or anything fancy. That's basic. Basic it's not only for beginners (pascal is, they don't have poke).  

> Basic principles of FP:
> * First-order functions
> * Pure functions
> * Function composition
> * Immutability

> A Basic programming language usually have:
> * Simple syntax without too much lookahead LALR(1).
> * Low quantity of keywords (I'm looking at you C#).
> * Statements and simple expressions.
> * Minimal control structures or none at all.

With that in mind we can start modeling our language. First we need to go way out to the past to get a fell of what Basic was before it became 'polluted' with OO concepts. Let's use Dartmouth basic as an example for what the syntax should have.

```
command:: label ' ' statement
statement::
    'LET' variable '=' expression
    'DIM' identifier '(' index ( ',' index )* ')' ( ',' identifier '(' index ( ',' index )* ')' )*
    'READ' variable ( ',' variable )*
    'DATA' number ( ',' number )*
    'PRINT' expression ( ',' expression )*
    'IF' expression 'THEN' label
    'FOR' variable '=' expression 'TO' expression ( 'STEP' expression )?
    'NEXT' variable
    'REM' comment
    'DEF' 'FN' identifier '(' variable ')' '=' expression
    'GOTO' label
    'GOSUB' label
    'RETURN'
    'STOP'
```

Our language will have:
* Strict evaluation 
* Call-by-Value
* Simple AST
* Reverse polish notation
* Mostly keyword based
* No semicolon
* Tailcall
* Hindley Milner type inference
