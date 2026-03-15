---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Passagem por referência

**Por valor** `f(vector<int> v)` — copia o container: $O(N)$. **Evitar.**

**Por `const&`** `f(const vector<int>& v)` — sem cópia, sem modificação. **Padrão para leitura.**

**Por `&`** `f(vector<int>& v)` — sem cópia, permite modificar in-place.

**Regra prática:** tipos primitivos (`int`, `char`, `bool`) por valor; containers e `string` por `const&` ou `&`.

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
// Ruim — copia o vetor inteiro a cada chamada!
void imprime(vector<int> v) { ... }

// Leitura — sem cópia
int soma(const vector<int>& v) {
    int s = 0;
    for (const auto& x : v) s += x;
    return s;
}

// Modificação in-place — sem cópia
void dobrar(vector<int>& v) {
    for (auto& x : v) x *= 2;
}

int main() {
    vector<int> v = {1, 2, 3, 4, 5};
    cout << soma(v);  // 15
    dobrar(v);        // v = {2, 4, 6, 8, 10}
}
```

</div>
