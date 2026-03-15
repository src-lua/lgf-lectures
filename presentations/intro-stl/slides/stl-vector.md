---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Array dinâmico `vector<T>`

**O que é?** Um array dinâmico que cresce e diminui de tamanho automaticamente.

**Quando usar?** Quase sempre! É a estrutura mais flexível e usada em CP.

**Observação:** `string` é essencialmente um `vector<char>` com operações extras.

| Operação | Custo |
|---|---|
| `push_back(x)` | $O(1)$ amortizado |
| `pop_back()` | $O(1)$ |
| `v[i]` | $O(1)$ |
| `size()` | $O(1)$ |
| `insert` / `erase` (meio) | $O(N)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
vector<int> v;

v.push_back(10);
v.push_back(20);
v.push_back(30);
// v = [10, 20, 30]

cout << v[0];      // 10
cout << v.size();  // 3
cout << v.back();  // 30

// Inicializar com tamanho e valor padrão
vector<int> zeros(5, 0); // [0, 0, 0, 0, 0]

// Range-based for
for (int x : v)
    cout << x << '\n';

// Remover último elemento
v.pop_back(); // v = [10, 20]

// Ordenar
sort(v.begin(), v.end());
```

</div>
