---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Dict `map<K,V>` `unordered_map<K,V>`

**`map<K, V>`:** Pares chave-valor ordenados por chave. $O(\log N)$ por operação.

**`unordered_map<K, V>`:** Hash table. $O(1)$ médio, sem ordenação.

**Regra geral:** Prefira `unordered_map` para lookup puro; use `map` quando precisar de ordenação ou `lower_bound`.

| Operação | `map` | `unordered_map` |
|---|---|---|
| `[key]`, `find` | $O(\log N)$ | $O(1)$ médio |
| `insert`, `erase` | $O(\log N)$ | $O(1)$ médio |
| Ordem garantida | Sim | Não |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
map<string, int> freq;
freq["ana"]++;
freq["bob"]++;
freq["ana"]++;

cout << freq["ana"]; // 2

// Iterar em ordem de chave
for (auto& [k, v] : freq)
    cout << k << ": " << v << '\n';

// Verificar existência sem criar entrada
if (freq.count("bob"))
    cout << "existe\n";

// Cuidado: [] cria a chave se não existir!
// Use .find() ou .count() para checar antes

// unordered_map — mesma API, mais rápido
unordered_map<int, int> mp;
mp[1] = 100;
mp[2] = 200;
cout << mp[1]; // 100
```

</div>

<style>
h1 { white-space: nowrap; }
</style>
