---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Two Pointers — Padrão Geral

**Subarray com soma $\le$ K** (elementos não-negativos):

Mantemos uma janela $[l, r]$: expandimos `r` e, quando a soma ultrapassa $K$, contraímos `l`.

**Por que funciona?** Com elementos não-negativos, aumentar `r` nunca diminui a soma e aumentar `l` nunca aumenta — a propriedade é monotônica.

**Outros usos clássicos:**

- Menor subarray com soma $\ge$ S
- Maior subarray sem elementos repetidos
- Contar subarrays com produto $< K$
- Mesclar dois arrays ordenados

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Contar subarrays com soma <= K
// (elementos não-negativos)
int l = 0, soma = 0, count = 0;

for (int r = 0; r < n; r++) {
    soma += a[r];

    while (soma > K) {
        soma -= a[l];
        l++;
    }

    // Todos os subarrays [x..r] com x em [l..r]
    // têm soma <= K
    count += (r - l + 1);
}
```

**Template geral:**

```cpp
int l = 0;
for (int r = 0; r < n; r++) {
    // Incorpora a[r] na janela

    while (/* janela inválida */) {
        // Remove a[l] da janela
        l++;
    }

    // Janela [l..r] é válida — processa
}
```

</div>
