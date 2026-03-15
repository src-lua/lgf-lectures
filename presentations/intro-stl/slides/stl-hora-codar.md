---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Hora de codar

**[CF 4C — Registration System](https://codeforces.com/problemset/problem/4/C)**

O Codeforces processa $n$ registros. Para cada nome de usuário:

- **Primeira ocorrência** → imprima `OK`
- **$k$-ésima ocorrência** ($k \ge 2$) → imprima `nome` + $(k-1)$

**Constraints:** $1 \le n \le 10^5$; nomes só com letras minúsculas.

::right::

<div style="transform: translateY(-1.5rem)">

**Entrada**

```
4
abacaba
acaba
abacaba
acab
```

**Saída**

```
OK
OK
abacaba1
OK
```

</div>
