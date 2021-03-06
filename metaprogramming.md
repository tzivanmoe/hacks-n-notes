# Metaprogramming

> Writing programs that manipulates programs as data

eg. compilers, transpilers

- build eslint-plugins
- build babel-plugins
- build codemods

# AST

## Explorer

- [AST Explorer](https://astexplorer.net/)
- [AST Visualizer from JointJS](http://resources.jointjs.com/demos/javascript-ast)

## Query

- [ESQuery](https://github.com/estools/esquery) like css selectors for AST

## Codemods

- [js codemod](https://github.com/cpojer/js-codemod) - collection of codemods

## Parts of a meta program

- Parser
- Parse Tree (AST - Abstract Synthax Tree)
- Code generator

### Work flow
- Parse
- Find
- Create
- Update
- Print

### Metaprograms
#### Esprima
- estraverse
- escodegen

#### ast-types
> To ensure data types while working with AST

#### recast

> To reprint code like if a human wrote it.
> It doesn't touches code that wasn't changed.



### Use cases

- insert logging in every function
- ESLint
- refactor deprecated code
- update legacy

#### Parser Generators
> Take language grammar and spits out a parser

- yak
- jyson
- [peg.js](http://pegjs.org/) 