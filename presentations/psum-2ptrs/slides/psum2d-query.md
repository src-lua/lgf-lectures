---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Prefix Sum 2D — Query $O(1)$

**Soma do retângulo** de $(r_1, c_1)$ até $(r_2, c_2)$ (0-indexado, inclusivo):

$$\text{soma} = P[r_2{+}1][c_2{+}1] - P[r_1][c_2{+}1] - P[r_2{+}1][c_1] + P[r_1][c_1]$$

**Inclusão-exclusão:** somamos o grande, subtraímos os dois lados fora, somamos de volta o canto que foi subtraído duas vezes.

```
P[r2+1][c2+1]  →  inteiro retângulo (0,0)..(r2,c2)
- P[r1][c2+1]  →  remove topo
- P[r2+1][c1]  →  remove esquerda
+ P[r1][c1]    →  adiciona canto (foi removido 2x)
```

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Query: soma de a[r1..r2][c1..c2] (0-indexado)
auto query = [&](int r1, int c1, int r2, int c2) {
    return p[r2+1][c2+1]
         - p[r1][c2+1]
         - p[r2+1][c1]
         + p[r1][c1];
};

int q;
cin >> q;
while (q--) {
    int r1, c1, r2, c2;
    cin >> r1 >> c1 >> r2 >> c2;
    cout << query(r1, c1, r2, c2) << '\n';
}
```

**Atenção:** com valores grandes, `long long` é necessário. Uma matriz $10^3 \times 10^3$ com valores $10^9$ pode chegar a $10^{15}$.

</div>
