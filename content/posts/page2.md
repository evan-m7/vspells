---
title: "VS Code Environment"
date: 2022-02-11T04:35:10-06:00
weight: 2
disableReadmoreNav: true
---

{{< lead >}} 
FORMULA Developments 
{{< /lead >}}

## Initial Version vs. Code Extension
Goal: Working toward a notebook-style interface

#### Representative Code Example
{{< code lang="html" >}}
domain Arith
    Id      ::= { NIL } + Integer + String.

    Name    ::= new (name: String, id: Id).

    Number  ::= new (op: Real
                    id: Id)

    UnApp   ::= new (op: ( NOT, NEG ),
                    arg1: any Expr,
                    id: Id).

    Sin     ::= new (arg: any Expr, id: Id).
    Cos     ::= new (arg: any Expr, id: Id).
    
    Expr    ::= Name + Nunber + UnApp - BinApp + Sin + Cos.
    
    Res     ::= (id: Id, res: Real).

   Res(id, res) :- n is Nunber, id = n.id, res = n.op.

   Res(id, res) :- e is BinApp, arg1 is Res, arg2 is Res,
                     e.op = ADD,
                     arg1.id = e.arg1.id,
                     arg2.id = e.arg2.id,
                     res = arg1.res + arg2.res,
                     id = e.id.

   Res(id, res) :- e is BinApp, arg1 is Res, arg2 is Res,
                     e.op = SUB,
                     arg1.id = e.arg1. id,
                     arg2.id = e.arg2.id,
                     res = arg1.res - arg2.res,
                     id = e.id.

   Res(id, res) :- e is BinApp, arg1 is Res, arg2 is Res,
                     e.op = DIV,
                     arg1.id = e.arg1.id,
                     arg2.id = e.arg2.id,
                     res = arg1.res / arg2.res,
                     id = e.id.

   Res(id, res) :- e is BinApp, arg1 is Res, arg2 is Res,
                     e.op = MUL,
                     arg1.id = e.arg1.1d,
                     arg2.id = e.arg2.id,
                     res = arg1.res * arg2.res,
                     id = e.id.

   Res(id, res) :-s is Sin, arg1 is Res,
                     arg1.id = s.arg.id,
                     val = arg1.res,
{{< /code >}}


#### Output After Running
{{< code lang="html" >}}
Creating file stream for file took: 0
Tokenizing for file took: 24
Parsing file took: 36
Visiting file took: 21
(Compiled) IntGraphs.4ml
0.36s.

   1s
   v 0.85

Environment variables

Programs in file root
+-- /
 +-. home
   +-- stephen
        git
     +-- formula- dotnet
      +-- Doc
       +-- Samples 1 file(s)
        | IntGraphs.4ml

Programs in env root
+-- /

All tasks
Id | Kind | Status | Result | Started | Duration
---|------|--------|--------|---------|--------- 
0.01s.

   query Gex E(x, x)
   v 0.15

Parsing text took: 0
Visiting text took: 0
Started query task with Id 1.
0.01s.

   ls tasks
    v 0.1s

All tasks
Id | Kind  | Status | Result | Started        | Duration
---|-------|--------|--------|----------------|--------- 
0  | Query | Done   | true | 2/1/2022 5:31 PM | 0.02s
1  | Query | Done   | true | 2/1/2022 5:32 PM | 0.00s
0.00s.

   exit
{{< /code >}}


