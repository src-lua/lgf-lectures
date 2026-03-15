---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Query de Soma — $O(1)$

**Soma do intervalo $[l, r]$** (0-indexado, inclusivo):

$$\text{soma}(l, r) = P[r+1] - P[l]$$

**Por quê funciona?**

$P[r+1] = A[0] + \cdots + A[r]$

$P[l] \;\;\;\;= A[0] + \cdots + A[l-1]$

Subtraindo: $P[r+1] - P[l] = A[l] + \cdots + A[r]$ ✓

**Exemplo com** `A = [3, 1, 4, 1, 5, 9, 2, 6]`:

`P = [0, 3, 4, 8, 9, 14, 23, 25, 31]`

- Soma $[2..5]$: $P[6] - P[2] = 23 - 4 = 19$ ✓
- Soma $[0..3]$: $P[4] - P[0] = 9 - 0 = 9$ ✓

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Construção
int n, q;
cin >> n;
vector<int> a(n), p(n + 1, 0);
for (int i = 0; i < n; i++) cin >> a[i];
for (int i = 0; i < n; i++)
    p[i + 1] = p[i] + a[i];

// Query: soma de a[l..r] inclusive
auto query = [&](int l, int r) {
    return p[r + 1] - p[l];
};

// Responder Q consultas
cin >> q;
while (q--) {
    int l, r;
    cin >> l >> r;
    cout << query(l, r) << '\n';
}
```

**Cuidado com overflow!** Se os valores forem grandes, use `long long`:

```cpp
vector<long long> p(n + 1, 0LL);
```

</div>
