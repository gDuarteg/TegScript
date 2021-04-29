# TegScript

## EBNF

BLOCK = "{", { COMMAND }, "}" ;

COMMAND = ( λ | ASSIGNMENT | PRINT | BLOCK | WHILE | IF), ";" ; 

WHILE = "ENQUANTO", "(", OREXPR ,")", COMMAND;

IF = "SE", "(", OREXPR ,")", COMMAND, (("SENAO", COMMAND) | λ );

ASSIGNMENT = IDENTIFIER, ("=" | "RECEBE"), EXPRESSION ; 

PRINT = "println", "(", OREXPR, ")" ; 

OREXPR = ANDEXPR, { ("||" | "OU"), ANDEXPR } ;

ANDEXPR = EQEXPR, { ("&&" | "E"), EQEXPR } ;

EQEXPR = RELEXPR, { ("==" | "IGUAL"), RELEXPR } ;

RELEXPR = EXPRESSION, { (">" | "<" | "MAIOR_QUE"| "MENOR_QUE"),  EXPRESSION }

EXPRESSION = TERM, { ("+" | "-" | "MAIS" | "MENOS"), TERM } ; 

TERM = FACTOR, { ("*" | "/" | "VEZES" | "DIVIDIDO"), FACTOR } ; 

FACTOR = (("+" | "-" | "MAIS" | "MENOS"| "!" ), FACTOR) | NUMBER | "(", OREXPR,  ")" | IDENTIFIER | READLN;

READLN = "readln", "(", ")";

IDENTIFIER = LETTER, { LETTER | DIGIT | "_" } ; 

NUMBER = DIGIT, { DIGIT } ; 

LETTER = ( a | ... | z | A | ... | Z ) ; 

DIGIT = ( 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 0 ) ;

