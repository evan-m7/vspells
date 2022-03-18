---
title: "Nix Support"
date: 2022-02-11T04:35:10-06:00
weight: 3
disableReadmoreNav: true
---

{{< lead >}} 
Adds nix language support for VSCode Editor
{{< /lead >}}

## Features
- Syntax Highlight
    - Nix code snippets inside markdown files also work.
- Full editing support with rnix-LSP
- When Language Server support is not enabled the following tools are used to
    - Formatting support
        - with the help of nixpkgs-format or other tools as specified by the nix.formatterPath option
    - Error Report
        - Using nix-instantiate errors reported
- Snippets
    