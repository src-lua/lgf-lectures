---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Hora de codar

**[CSES 1643 — Maximum Subarray Sum](https://cses.fi/problemset/task/1643)**

Dado um array de $N$ inteiros (podendo ser negativos), encontre a maior soma de um subarray contíguo.

**Constraints:** $1 \le N \le 2 \times 10^5$; $-10^9 \le A_i \le 10^9$

**Dica:** algoritmo de Kadane — $O(N)$, sem sliding window explícita. Ótimo para fixar o padrão de janela variável.

**Alternativa (sliding window fixa):**

**[CSES 1141 — Playlist](https://cses.fi/problemset/task/1141)** — maior subarray sem elementos repetidos. Use Two Pointers + `set` ou `map` para contar frequências.

::right::

<div style="transform: translateY(-1.5rem)">

**Entrada (Maximum Subarray Sum)**

```
8
-1 3 -2 5 3 -5 2 2
```

**Saída**

```
9
```

*(subarray $[3, -2, 5, 3]$ com soma $9$)*

**Entrada (Playlist)**

```
8
1 2 1 3 2 7 4 2
```

**Saída**

```
5
```

*(subarray $[1, 3, 2, 7, 4]$ com $5$ elementos distintos)*

</div>
