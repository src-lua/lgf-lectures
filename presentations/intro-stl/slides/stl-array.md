---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Array estático `array<T, N>`

**O que é?** Wrapper sobre array C com tamanho **fixo em tempo de compilação**.

**Quando usar?** Quando o tamanho é constante e conhecido — mais seguro que `T arr[N]` pois tem `.size()`, `.begin()` e `.end()`.

**Observação:** Não cresce. Para tamanho dinâmico, use `vector<T>`.

| Operação | Custo |
|---|---|
| `a[i]`, `a.at(i)` | $O(1)$ |
| `a.size()` | $O(1)$ |
| `a.front()`, `a.back()` | $O(1)$ |
| `a.fill(val)` | $O(N)$ |
| `sort(a.begin(), a.end())` | $O(N \log N)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
array<int, 5> a = {3, 1, 4, 1, 5};

cout << a[0];        // 3
cout << a.size();    // 5
cout << a.front();   // 3
cout << a.back();    // 5

// Preencher com valor padrão
array<int, 5> zeros;
zeros.fill(0);       // {0, 0, 0, 0, 0}

// Sort funciona normalmente
sort(a.begin(), a.end());
// a = {1, 1, 3, 4, 5}

// Iterar
for (int x : a) cout << x << ' ';

// Passar para função sem perder o tamanho
void f(array<int, 5>& arr) {
    cout << arr.size(); // 5
}
```

</div>
