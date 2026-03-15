---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Two Pointers — Ideia

**Problema motivador:** encontrar todos os pares $(i, j)$ com $i < j$ tais que $A[i] + A[j] = T$ em um array **ordenado**.

**Força bruta:** dois loops → $O(N^2)$.

**Two Pointers:** mantemos dois ponteiros `l` e `r` nas extremidades. A cada passo, avançamos um deles:

- $A[l] + A[r] = T$ → encontrou! avança `l`, recua `r`
- $A[l] + A[r] < T$ → soma pequena, avança `l`
- $A[l] + A[r] > T$ → soma grande, recua `r`

**Complexidade:** $O(N)$ — cada ponteiro anda no máximo $N$ passos.

**Pré-condição:** funciona em arrays **ordenados** ou quando a propriedade é **monotônica** (ao mover um ponteiro, a resposta só piora ou só melhora).

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Par com soma T em array ordenado
sort(a.begin(), a.end());
int l = 0, r = n - 1;

while (l < r) {
    int s = a[l] + a[r];
    if (s == T) {
        cout << a[l] << ' ' << a[r] << '\n';
        l++; r--;
    } else if (s < T) {
        l++;  // precisa de soma maior
    } else {
        r--;  // precisa de soma menor
    }
}
```

**Visualização:**

```
A = [1, 2, 3, 4, 6, 8, 9]   T = 10
     ^                   ^
     l                   r   → 1+9=10 ✓
         ^           ^
         l           r       → 2+8=10 ✓
             ^   ^
             l   r           → 3+6= 9 < 10 → l++
               ^  ^
               l  r          → 4+6=10 ✓
```

</div>
