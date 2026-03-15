---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Strings `string`

**O que é?** Uma sequência mutável de caracteres com operações de texto embutidas.

**Quando usar?** Processamento de texto, parsing de entrada, comparação e manipulação de strings.

**Dica:** `find()` retorna `string::npos` se não encontrar — sempre compare com ele.

| Operação | Custo |
|---|---|
| `s[i]`, `s.back()` | $O(1)$ |
| `s.size()` | $O(1)$ |
| `s + t` (concat) | $O(N)$ |
| `s.substr(pos, len)` | $O(N)$ |
| `s.find(sub)` | $O(N \cdot M)$ |

::right::

<div style="transform: translateY(-1.5rem)">

```cpp
string s = "hello";

s += " world";           // "hello world"
cout << s.size();        // 11
cout << s[0];            // 'h'
cout << s.back();        // 'd'

// Substring
cout << s.substr(6, 5);  // "world"

// Busca — string::npos se não achar
size_t pos = s.find("world");
if (pos != string::npos)
    cout << pos;         // 6

// Iterar por caracteres
for (char c : s) cout << c;

// Converter
string n = to_string(42); // "42"
int x    = stoi("123");   // 123
```

</div>
