# BARES

Basic ARithmetic Expression Evaluator based on Stacks.

Write about the program here...

**TODO: Finish this section later.**

## Compilation

Write about requirements to compile this code, how to compile it and how to use it.

**TODO: Finish this section later.**

## Expressions

Write about possible input expressions, operator precedence order and give some examples of valid expressions and its results. 

**TODO: Finish this section later.**

## Expression's Parsing
In order to validate and process the input expression, we need to specify the tokens and grammar used to define the desired language.

### Tokens
The following table presents the tokens defined for this application. Its first column shows the tokens name, and the second column specifies a regex expression to recognize them.

| Token Name    | Regex            |
|:------------: |:---------------:|
| NUM           | `[0-9]*`         |
| ADD_OP        | `'+'|'-'`        |
| MULT_OP       | `'*'|'/'|'%'`    |
| EXP_OP        | `'^'`            |
| LPAR          | `'('`            |
| RPAR          | `')'`            |

### Grammar
The grammar below defines the language for the expressions used in this application considering the operator precedence defined previously.

<pre>
<code>
&lsaquo;expr&rsaquo;      &xrarr;  &lsaquo;multExpr&rsaquo; ADD_OP &lsaquo;expr&rsaquo;
&lsaquo;multExpr&rsaquo;  &xrarr;  &lsaquo;expExpr&rsaquo; MULT_OP &lsaquo;multExpr&rsaquo;
&lsaquo;expExpr&rsaquo;   &xrarr;  &lsaquo;unaryExpr&rsaquo; EXP_OP &lsaquo;term&rsaquo;
&lsaquo;unaryExpr&rsaquo; &xrarr;  ADD_OP &lsaquo;term&rsaquo;
&lsaquo;term&rsaquo;      &xrarr;  NUM | LPAR &lsaquo;expr&rsaquo; RPAR</code>
</pre>