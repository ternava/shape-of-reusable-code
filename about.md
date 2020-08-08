---
layout: pagemod
title: Syntax
permalink: /syntax/
---


### VM-DSL Syntax

The VM-DSL language syntax for defining variation points with their variants and modeling the implemented variability of a variability-rich system in terms of them.

```
<vps-list> ::= <vp> | <vp> <EOL> <vps-list> 

<variants-list> ::= <variant> | <variant> <EOL> <variants-list> 

<vp> ::= <vp-name> `=' <vp-type> `(' `asset' `(' <tag> `)' `)'

<variant> ::= <variant-name> `=' `Variant' `(' `asset' `(' <tag> `)' `)'

<vp-name> | <variant-name> := "string name"

<vp-type> ::= `VP' | `oVP' | `tVP' | `nVP'

<tag> ::= <class-name> | <method-name> | <field-name>

<fragment> ::= `fragment' `(' <tvm-name> `)' `{' 
    <vp-name> `is' <logical-relation> `with_variants' `('`{'<variants>`}'`)'
    `use' <technique> `with_binding' <binding-time> `and_evolution' <evolution> <EOL> 
`}'

<tvm-name> ::= <class-name> | <file-name> | <package-name> | "string name"

<logical-relation> ::= `MND' | `OPT' | `ALT' | `MUL'

<variants> ::= <variant-name> | <variant-name> `,' <variants> 

<technique> ::= `Inheritance' | `Overloading' | `Strategy_Pattern' |
                `Template_Pattern' | "etc"

<binding-time> ::= `Compile' | `StartUp' | `Runtime' | "etc"

<evolution> ::= `Open' | `Close'
```

The VM-DSL language syntax for defining trace links between variation points and variants at the implemenetation to features at the specification.

```
<trace-links> ::= `traces' `{' <links> `}'

<links> ::= <vp-name> `implements' <feature-name> | 
            <variant-name> `implements' <feature-name>

<vp-name> | <variant-name> | <feature-name> := "string name"
```

The manuscript with diff: [here](assets/files/manuscript-diff.pdf).

### Bibliography

  <ul>
    <li>[1] Xhevahire Tërnava and Philippe Collet.
      <em>On the Diversity of Capturing Variability at the Implementation Level.</em>
      In the 21st International Systems and Software Product Line Conference-Volume B. 2017. ACM Press.</li>
    <li>[2] Xhevahire Tërnava and Philippe Collet. <em>Tracing Imperfectly Modular Variability in Software Product Line
      Implementation.</em> In International Conference on Software Reuse. 2017. Springer, Cham. </li>
    <li>[3] Xhevahire Tërnava and Philippe Collet. 
    <em>Early Consistency Checking Between Specification and Implementation Variabilities.</em> 
    In Proceedings of the 21st International Systems and Software Product Line Conference-Volume A. 2017. ACM Press.</li>
    <li>[4] Xhevahire Tërnava. 
    <em>Handling variability at the code level: modeling, tracing and checking consistency.</em> PhD dissertation, 2017.</li>
  </ul>
