---
title: "Tree-sitter Grammar"
date: 2022-02-11T04:35:10-06:00
weight: 4
disableReadmoreNav: true
---

{{< lead >}} 
Tree-sitter grammar for Formula using vscode-anycode
{{< /lead >}}

## Why Anycode for Formula?
A <a href="https://tree-sitter.github.io/tree-sitter/" target="_blank">Tree-sitter</a>-based language extension that inaccurately implements popular features like "Outline & Breadcrumbs", "Go to Symbol in Workspace", "Document Highlights" and more. This extension should be used when running in enviroments that don't allow for running actual language services, like Formula


### Anycode Features
The features provided by this extension are meant to be better than full-text search, but fall short when compared to real language services. We refer to this as "partial mode" and anycode will show a language status item when inaccurate language support is active.

Anycode identifies and compares usages and declarations.

Outline - A parse tree itself is an outline. However, it is too detailed and anycode selects declarations like functions, classes with its memebers, interfaces etc.

Go to Symbol - Anything that would show in outline (declarations) is stored in a trie so that it can be found by typing names or partial names of declarations. How well this works across file depends on the anycode.symbolIndexSize-setting - it defauls to 100 and defines how many files are eagerly fetched and analyzed.

Go to Definition - Works just like "Go to Symbol" but it uses the current identifier as the name to find declarations for. This isn't semantic and depending on your project yields false positives, e.g it will find all run-methods and not just Runnable#run etc

Completions - Any identifier of the current document and the names of all known declarations are always suggested as completions. So, no precise member-completion but identifiers.

Expand/Shrink Selection - Solely based on parse trees. It finds the node at the current position and returns all parents as selection.

Syntax Validation - Tree-sitter parsers can recover from malformed source code. In case error nodes are inserted into the parse tree and anycode can report them as diagnostics. Note that validation is off by default and that it must be enabled via the anycode.language.features#diagnostics-setting.

Document Highlights - For local variables and function arguments usages in their scope are computed and highlighted. If that's not possible, all identifiers with the same name are highlighted - 1 only identifier based highlights implemented

Reference Search - All usages, such as function-calls or member-accesses, are kept in a trie which is later used for reference search. Like "Go to Symbol" its result depend on the anycode.symbolIndexSize-setting.

Last, there is the anycode.language.features-setting which controls what feature is enabled or disabled - either for all or just specific languages.