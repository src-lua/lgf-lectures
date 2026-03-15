---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Prefix Sum 2D — Construção

**Problema:** dada uma matriz $N \times M$, responder somas de subrregiões retangulares em $O(1)$.

**Definição:** $P[i][j]$ = soma de todos os elementos no retângulo de $(0,0)$ até $(i-1, j-1)$.

**Fórmula de construção** (inclusão-exclusão):

$$P[i][j] = A[i-1][j-1] + P[i-1][j] + P[i][j-1] - P[i-1][j-1]$$

Bordas: $P[0][j] = P[i][0] = 0$ (sentinelas).

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
int n, m;
cin >> n >> m;

vector<vector<int>> a(n, vector<int>(m));
vector<vector<long long>> p(n+1, vector<long long>(m+1, 0));

for (int i = 0; i < n; i++)
    for (int j = 0; j < m; j++)
        cin >> a[i][j];

// Construção O(NM)
for (int i = 1; i <= n; i++)
    for (int j = 1; j <= m; j++)
        p[i][j] = a[i-1][j-1]
                + p[i-1][j]
                + p[i][j-1]
                - p[i-1][j-1];
```

**Intuição:** somar retângulo que chega em $(i,j)$ a partir dos retângulos acima e à esquerda, descontando a sobreposição.

</div>
