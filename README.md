# Webeye

## Webized reasoning

[Webeye](https://github.com/IDLabResearch/Webeye) is using [ISO Prolog notation](https://en.wikipedia.org/wiki/Prolog#ISO_Prolog):

TERM            | Examples
----------------|---------
IRI             | `'http://example.org/etc#Socrates'`
VARIABLE        | `X` `_abc`
LITERAL         | `"abc"` `1.52` `1e-18` `pi` `dt("2022-01-15",'http://www.w3.org/2001/XMLSchema#date')`
LIST            | `[TERM,...]` `[TERM,...\|LIST]`
TRIPLE          | `IRI(TERM,TERM)`
GRAPH           | `TRIPLE,...`

CLAUSE          | Examples
----------------|---------
ASSERTION       | `TRIPLE.` `true => GRAPH.`
FORWARD_RULE    | `GRAPH => GRAPH.`
QUERY           | `GRAPH => true.`
ANSWER          | `GRAPH => true.`
INFERENCE_FUSE  | `GRAPH => false.`
BACKWARD_RULE   | `TRIPLE :- GRAPH,`[PROLOG](http://tau-prolog.org/documentation#prolog)`.`

Webeye performs forward chaining for a `FORWARD_RULE` and backward chaining for a `BACKWARD_RULE`.

Queries are posed and answered as `GRAPH => true.` so the answers are also queries be it with
some parts substituted and eventually containing more variables than in the original query.
This forms a dialogue that leads to a sufficient answer, supported by proof steps, so that action can take place.

## Installation and test:
```
$ git clone https://github.com/IDLabResearch/Webeye
$ cd Webeye
$ npm install tau-prolog
$ cd examples
$ ./test
```

## Background

- Book of Markus Triska: [The Power of Prolog](https://www.metalevel.at/prolog)
