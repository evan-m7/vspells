---
title: "Symbolic Execution"
date: 2022-02-11T04:35:10-06:00
weight: 1
---

{{< lead >}} 
### What Does Code Below Show?
- Component --> Software Components 
- Processor --> Hardware Processors
- Mapping --> Mapping Between The Two

{{< lead >}}
Outcome is one inference rule describing a bad mappings shown by models (m & pm) of Mapping. 
{{< /lead >}}
{{< /lead >}}

### FORMULA: Initial Version of Symbolic Executer Engine
Representative Example 

{{< code lang="html" >}}
domain Mapping
{
	Component ::= new (id: Integer, utilization: Real).
	Processor ::= new (id: Integer).
	Mapping   ::= new (c: Component, p: Processor).
	
	badMapping :- p is Processor,
            	  s = sum (0.0, { c.utilization |
                                  c is Component, Mapping (c, p) }), s > 100.
  
  conforms no badMapping.
}

model m of Mapping
{
	c1 is Component (0, 10).
	c2 is Component (1, 91).
	p1 is Processor (0).
	Mapping (c1, p1).
	Mapping (c2, p1).
}

partial model pm of Mapping
{
	c1 is Component (0, x).
	c2 is Component (1, 90).
	p1 is Processor (0).
	Mapping (c1, p1).
	Mapping (c2, p1).
}
{{< /code >}}

### Going Forward

- Support many additional language features, work is ongoing
- Next step: recursive rules