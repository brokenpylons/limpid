# Limpid
Toy programming language aimed at education. 

Labeled BNF:

```
_.           unit: program*

Program.     program: 'program' block

Assignment.  stmt: ID ':' expr ';'
If.          stmt: 'if' parent block
While.       stmt: 'while' parent block
Print.       stmt: 'print' expr ';'

_.           parent: '(' expr ')'

_.           block: '{' stmt* '}'

Lt.          expr: expr '>' expr1
Gt.          expr: expr '<' expr1
Eq.          expr: expr '=' expr1
_.           expr: expr1

Plus.        expr1: expr1 '+' expr2
Minus.       expr1: expr1 '-' expr2
_.           expr1: expr2

Times.       expr2: expr2 '*' expr3
Divides.     expr2: expr2 '/' expr3
_.           expr2: expr3

Number.      expr3: NUMBER
Id.          expr3: ID
Input.       expr3: 'input'
_.           expr3: '(' expr ')'

token NUMBER [0-9]+
token ID     [a-zA-Z]+

```

Example:
```
program {
  i: 1;
  while (i < 5) {
    print i;
    i: i + 1;
  }
}
```
