OBJY = parser.y

OBJL = scanner.l

PRG = parser

YACC = yacc -d

LEX = lex

CC = cc

parser: y.tab.o lex.yy.o symtab.o llvmcommands.o
	$(CC) -o $(PRG) y.tab.o lex.yy.o symtab.o llvmcommands.o -ll

y.tab.o: y.tab.c
	$(CC) -c -o y.tab.o y.tab.c

lex.yy.o: lex.yy.c
	$(CC) -c -o lex.yy.o lex.yy.c

symtab.o: symtab.c
	$(CC) -c -o symtab.o symtab.c

llvmcommands.o: llvmcommands.c
	$(CC) -c -o llvmcommands.o llvmcommands.c

y.tab.c: $(OBJY)
	$(YACC) $(OBJY)

lex.yy.c: $(OBJL)
	$(LEX) $(OBJL)

clean:
	rm $(PRG) y.tab.c lex.yy.c y.tab.h y.tab.h *.o *.h~ *.c~ *.y~ *.o~