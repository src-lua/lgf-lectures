---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Prefix XOR

**Mesma ideia do Prefix Sum**, trocando adição por XOR ($\oplus$).

$$X[0] = 0$$
$$X[i] = X[i-1] \oplus A[i-1]$$

**Query $\oplus [l, r]$:**

$$X[r+1] \oplus X[l]$$

Funciona porque $x \oplus x = 0$ — o XOR cancela a si mesmo:

$X[r+1] \oplus X[l] = (A[0] \oplus \cdots \oplus A[r]) \oplus (A[0] \oplus \cdots \oplus A[l-1])$

Os termos $A[0..l-1]$ se cancelam, restando $A[l] \oplus \cdots \oplus A[r]$.

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
int n, q;
cin >> n;
vector<int> a(n), x(n + 1, 0);
for (int i = 0; i < n; i++) cin >> a[i];

// Construção O(N)
for (int i = 0; i < n; i++)
    x[i + 1] = x[i] ^ a[i];

// Query XOR de a[l..r] em O(1)
auto query = [&](int l, int r) {
    return x[r + 1] ^ x[l];
};

cin >> q;
while (q--) {
    int l, r;
    cin >> l >> r;
    cout << query(l, r) << '\n';
}
```

**Obs.:** XOR não tem problema de overflow — opera bit a bit.

</div>
