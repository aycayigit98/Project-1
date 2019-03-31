# Project-1
Assignment 1 for Programming Language Course

Project 1: Lexical Analyzer
Course: Programming Languages

20150807010  Gizem Ünlü
20160808051	Ayça Yiğit



PART A:
We decided to call our language simply “MyLang”. Down below are the list of definitions which are going to have their place in the language.

DIGIT			[ 0-9 ]
NUMBER		{DIGIT}+
INT			-?{NUMBER}
FLOAT			{INT}”.”{NUMBER}
LETTER			[ a - zA – Z ]
WORD			{LETTER}+
IDENT			({LETTER} | )({WORD} | {NUMBER})*
HEX			[ 0 – 9a - fA - F ]
CHAR_ENCODED	“\\\\”|”\\\””|”\\’”|”\\n”|”\\t”|”\\f”|”\\v”|”\\r”|”\\a”|”\\b”|\\x”{HEX}{2}|\\u{HEX}{4}|”\\U”{HEX}{8}
CHAR			‘({CHAR_ENCODED} | [ ^ ‘ ])’
STRING			“\””({CHAR_ENCODED} | [ ^\” ])*”\””
KEYWORD		if|then|else|elseif|while|do|breack|continue|print|scan
TYPE			int|float|double|char|string|boolean
BOOL			“and” | ”or” | ”not” | ”not=” | ”==” | ”>” | ”<” | ”>_” | ”_<” | “->”| “<->”
OPERATOR		“ + ” | ” - ” | ” * ” | ” / ” | ” ^ ” | ” % ” | “<<” | ”>>”
COMMENT		“^_^”
OTHER			“{” | “}” | “(” | “)” | “[” | “]” | “=” | “;” | “:” | “?” | “.” | “,” 

Backus-Naur Form (BNF)
<digit> ::= 0…9
<integer> ::= <digit> | <digit><integer>
<expression op> ::= + | -
<mult op> ::= * | /
<letter> ::= A|B|C|….a|b|c
<word> ::= <letter>|<letter><word>
<identifier> ::= <letter> | <letter> <identifier>
<term> ::= <identifier> | <integer> | (expression) |- <term>
<mult> ::= <term> | <term> <mult op> <mult>
<expression> ::= <term> | <identifier> <expression op> <mult>


PART B:

%{
        #include<stdio.h>
%}

%%
[a-zA-Z]                printf("LETTER");
[0-9]                   printf("NUMBER");
%%

int yywrap()
{
return 0;
}

int main()
{
printf("Enter something");
yylex();
}

PART C:


