---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Construção do Prefix Sum

**Ideia:** $P[i]$ = soma de todos os elementos de $A[0]$ até $A[i-1]$.

$$P[0] = 0$$
$$P[i] = P[i-1] + A[i-1], \quad i \ge 1$$

O array $P$ tem **tamanho $N+1$**, com $P[0] = 0$ como sentinela — simplifica o cálculo das queries.

**Construção em $O(N)$:**

```
A = [3,  1,  4,  1,  5,  9,  2,  6]
P = [0,  3,  4,  8,  9, 14, 23, 25, 31]
```

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
int n;
cin >> n;

vector<int> a(n), p(n + 1, 0);

for (int i = 0; i < n; i++)
    cin >> a[i];

// Construir prefix sum (1-indexado em P)
for (int i = 0; i < n; i++)
    p[i + 1] = p[i] + a[i];

// p[i] = soma de a[0..i-1]
// p[0] = 0 (sentinela)
// p[1] = a[0]
// p[2] = a[0] + a[1]
// ...
// p[n] = a[0] + ... + a[n-1]
```

</div>
