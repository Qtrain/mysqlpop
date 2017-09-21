# MySQLPop


MySQL parser (based on SQLPop, a SQLite query parser)

## Goal

Provide enough support for MySQL-flavored SQL to provide a base for higher level tooling (query fingerprints, read write splitting proxies, intrusion detection, etc).

## MySQL Flavor

- [x] Set Variable statements (`set @foo = 1`)
- [x] MySQL-style variables (`@@global.read_only`)
- [x] Variable assignment in expressions (`select @id := @id +1`)
- [x] MySQL-style backslash escapes in strings (`'foo\'bar'`)
- [x] Removed SQLite specific variable syntax
- [x] Parameters/Placeholders (`select foo from bar where baz > ?`)
- [ ] Prepared statements
- [ ] Procedures
- [ ] Transactions
- [ ] XA Transactions
- [ ] SHOW statements
- [ ] Change autoincrement keyword
- [ ] MySQL style create table (UNIQUE/FOREIGN key etc)
- [ ] SELECT into variables/dumpfiles/procedures
- [ ] DO statements
- [ ] CALL statements
- [ ] CHECK statements
- [ ] FLUSH statements
- [ ] GRANT/REVOKE statements
- [ ] HANDLER statements
- [ ] LOAD DATA statements
- [ ] LOCK/UNLOCK statements
- [ ] RENAME statement
- [ ] USE statement
- [ ] TRUNCATE statement

And maybe some other differences we'll run into after we've knocked out this list.

* [LARLPOP and custom lexer](https://github.com/nikomatsakis/lalrpop/issues/39)
* [SQLite tokenizer](http://www.sqlite.org/src/artifact?ci=trunk&filename=src/tokenize.c)
* [SQLite parser](http://www.sqlite.org/src/artifact?ci=trunk&filename=src/parse.y)
* [SQLite BNF grammar](http://www.sqlite.org/docsrc/doc/trunk/art/syntax/all-bnf.html)
* [SQLite syntax diagram data](http://www.sqlite.org/docsrc/doc/tip/art/syntax/bubble-generator-data.tcl?mimetype=text/plain)

Currenly, only the lexer is complete and tested.
The parser is almost complete (see [LARLPOP issues](https://github.com/nikomatsakis/lalrpop/issues/156)).
