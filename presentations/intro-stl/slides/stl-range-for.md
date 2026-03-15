---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Range-based `for`

**`for (auto x : c)`**: copia cada elemento; ok para `int`/`char`, evitar para objetos grandes.

**`for (auto& x : c)`**: referência; permite **modificar** elementos.

**`for (const auto& x : c)`**: referência constante; leitura sem cópia — **preferir** para `string`, `pair`, structs.

Funciona com qualquer container que tenha `begin()`/`end()`.

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
vector<int> v = {1, 2, 3, 4, 5};

// Cópia — ok para int
for (auto x : v)
    cout << x << ' ';

// Referência — modifica elementos
for (auto& x : v)
    x *= 2;  // v = {2, 4, 6, 8, 10}

// Const ref — leitura eficiente
for (const auto& x : v)
    cout << x << ' ';

// Pair em map — structured binding (C++17)
map<string, int> freq = {{"a", 1}, {"b", 2}};
for (const auto& [k, val] : freq)
    cout << k << ": " << val << '\n';
```

</div>
