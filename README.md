# TegScript | Relatório

Linguagem de programação em português para o fácil entendimento da linguagem por pessoas iniciantes na área de programação que não dominam o inglês, e não requerem de funções mais complexas de uma linguagem.

Para sua implementação foi utilizado como base o compilador de C desenvolvido na aula de Lógica da Computação

Exemplos de uso podem ser encontrados na pasta Tests/

## Instruções

Crie um arquivo e execute o comando

`python main.py <file.txt>`

Para ser executado, deve existir uma função chamada main, e não deve existir comandos fora de funções.

## EBNF

FUNCDEFBLOCK = (λ | TYPE, IDENTIFIER, "(", {TYPE, IDENTIFIER}, {(",", TYPE, IDENTIFIER)}, ")", COMMAND);

BLOCK = "{", { COMMAND }, "}" ;

COMMAND = ( λ | ASSIGNMENT | PRINT | BLOCK | WHILE | IF | RETURN), ";" ; 

RETURN = "retorna", OREXPRESSION

WHILE = "enquanto", "(", OREXPR ,")", COMMAND;

IF = "se", "(", OREXPR ,")", COMMAND, (("senao", COMMAND) | λ );

ASSIGNMENT = IDENTIFIER, ("="), EXPRESSION ; 

TYPE = TYPES, IDENTIFIER ;

PRINT = "printa", "(", OREXPR, ")" ; 

OREXPR = ANDEXPR, { ("||"), ANDEXPR } ;

ANDEXPR = EQEXPR, { ("&&"), EQEXPR } ;

EQEXPR = RELEXPR, { ("=="), RELEXPR } ;

RELEXPR = EXPRESSION, { (">" | "<"),  EXPRESSION }

EXPRESSION = TERM, { ("+" | "-" | "MAIS" | "MENOS"), TERM } ; 

TERM = FACTOR, { ("*" | "/" | "VEZES" | "DIVIDIDO"), FACTOR } ; 

FACTOR = (("+" | "-" | "MAIS" | "MENOS"| "!" ), FACTOR) | NUMBER | "(", OREXPR,  ")" | IDENTIFIER | READLN;

READLN = "ler", "(", ")";

IDENTIFIER = LETTER, { LETTER | DIGIT | "_" } ; 

NUMBER = DIGIT, { DIGIT } ; 

LETTER = ( a | ... | z | A | ... | Z ) ; 

DIGIT = ( 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 ) ;

TYPES = ("intero" | "booleano", "texto") ;

BOOL = ("verdade" | "falso")


## Diagrama Sintatico

![alt text](https://github.com/gDuarteg/TegScript/blob/main/ds.png)

