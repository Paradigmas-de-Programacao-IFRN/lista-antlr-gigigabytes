# Questão 1

## Instalar o ANTLR 

> pip install antlr4-tools

## Enunciado

Usando a gramática abaixo, crie três programas diferentes.

````antlr
grammar Gramatica1;
prog: stat+;
stat: expr NEWLINE
    | ID '=' expr NEWLINE
    | 'escreva' expr NEWLINE
    | NEWLINE
    ;

expr: expr ('*'|'/') expr
    | expr ('+'|'-') expr
    | INT
    | ('leia_texto' | 'leia_numero')
    | ID
    | '(' expr ')'
    ;

ID : [a-zA-Z]+ ; // match identifiers
INT : [0-9]+ ; // match integers
NEWLINE:'\r'? '\n' ; // return NL to parser (is end-statement signal)
WS : [ \t]+ -> skip; // toss out whitespace
````

## Para testar

Use o comando `antlr4-parse`

````
antlr4-parse Gramatica1.g4 prog -gui
escreva 10+20
^D
````

ou 

````
antlr4-parse Gramatica1.g4 prog -gui olamundo.txt
````

Se estiver só no modo texto use

````
antlr4-parse Gramatica1.g4 prog -tree
escreva 10+20
^D
````
