---
layout: default
---

<LogoBar variant="black" position="header" align="right" />

# Primeiro Código

<div class="grid grid-cols-2 gap-12 absolute inset-x-12 top-12   bottom-8">

<div class="flex flex-col justify-center">

````md magic-move
```cpp {*}
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cin >> name;

    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
```

```cpp {*}
#include <iostream>
#include <string>

using namespace std;

int main() {
    std::string name;
    std::cin >> name;

    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
```

```cpp {*}
#include <iostream>
#include <string>

using namespace std;

int main() {
    string name;
    cin >> name;

    cout << "Hello, " << name << "!" << endl;

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

int main() {
    string name;
    cin >> name;

    cout << "Hello, " << name << "!" << endl;

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);

    string name;
    cin >> name;

    cout << "Hello, " << name << "!" << endl;

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);

    string name;
    cin >> name;

    cout << "Hello, " << name << "!" << '\n';

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);

    int tc; cin >> tc; while (tc--) {
        string name;
        cin >> name;
        
        cout << "Hello, " << name << "!" << '\n';
    }

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);

    freopen("input.txt", "r", stdin);
    freopen("output.txt", "w", stdout);

    int tc; cin >> tc; while (tc--) {
        string name;
        cin >> name;

        cout << "Hello, " << name << "!" << '\n';
    }

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

using ll  = long long;
using pii = pair<int, int>;
using vi  = vector<int>;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);

    freopen("input.txt", "r", stdin);
    freopen("output.txt", "w", stdout);

    int tc; cin >> tc; while (tc--) {
        string name;
        cin >> name;

        cout << "Hello, " << name << "!" << '\n';
    }

    return 0;
}
```

```cpp {*}
#include <bits/stdc++.h>

using namespace std;

using ll  = long long;
using pii = pair<int, int>;
using vi  = vector<int>;

int main() {
    ios::sync_with_stdio(false);
    cin.tie(0);
    cout << fixed << setprecision(10);

    freopen("input.txt", "r", stdin);
    freopen("output.txt", "w", stdout);

    int tc; cin >> tc; while (tc--) {
        string name;
        cin >> name;

        cout << "Hello, " << name << "!" << '\n';
    }

    return 0;
}
```
````

</div>

<div class="flex flex-col justify-center">
<Transition name="fade" mode="out-in">

<div v-if="$clicks === 0" key="s0">

Código C++ com o prefixo `std::` em tudo. É o jeito mais explícito: deixa claro de onde cada nome vem, mas é verboso demais para usar em contest.

</div>
<div v-else-if="$clicks === 1" key="s1">

`using namespace std;` importa todos os nomes do namespace `std` para o escopo global: como dizer "já sei de onde vêm as coisas, não preciso repetir `std::` o tempo todo".

</div>
<div v-else-if="$clicks === 2" key="s2">

Com `using namespace std;`, escrevemos `string`, `cin`, `cout` diretamente. Em programação competitiva, esse é o padrão universal.

</div>
<div v-else-if="$clicks === 3" key="s3">

`#include <bits/stdc++.h>` inclui **tudo** da biblioteca padrão de uma vez: `<vector>`, `<string>`, `<algorithm>`, tudo. 

É uma extensão do **GCC** — não faz parte do padrão C++ e não funciona no MSVC nem no Clang sem configuração extra. Em CP isso não importa: os juízes online usam GCC, então economiza tempo e garante que nenhum include vai faltar.

</div>
<div v-else-if="$clicks === 4" key="s4">

Por padrão, `cin`/`cout` são sincronizados com `scanf`/`printf` do C, o que tem um **alto custo de performance**. A cada operação, o programa sincroniza os buffers de ambas as bibliotecas.

- `ios::sync_with_stdio(false)` desativa essa sincronização
- `cin.tie(0)` desvincula `cin` de `cout`, eliminando flushes desnecessários

Com $n \geq 10^5$ linhas de input, sem isso → **TLE**.

</div>
<div v-else-if="$clicks === 5" key="s5">

`endl` faz duas coisas: insere `\n` **e** força um flush do buffer de saída. Em loops com muitas escritas, isso é devastador para a performance.

Use sempre `'\n'`, o buffer é liberado automaticamente no final do programa.

</div>

<div v-else-if="$clicks === 6" key="s6">

Muitos problemas têm múltiplos casos de teste: a primeira linha informa quantos são (`tc`), e o código processa cada um no loop. O `while (tc--)` decrementa `tc` e continua enquanto for positivo: padrão universal em CP.

</div>
<div v-else-if="$clicks === 7" key="s7">

Para testar localmente sem colar input no terminal, `freopen` redireciona `stdin`/`stdout` para arquivos. Antes de submeter, basta remover essas duas linhas: o juiz online usa `stdin`/`stdout` normalmente.

</div>
<div v-else-if="$clicks === 8" key="s8">

Aliases de tipo eliminam ruído visual no código:

- `ll` no lugar de `long long`
- `pii` no lugar de `pair<int,int>`
- `vi` no lugar de `vector<int>`

São definidos com `using`, a sintaxe moderna do <br> $\text{C++11}$: equivalente ao `typedef`, mas mais legível.

</div>
<div v-else-if="$clicks === 9" key="s9">

`fixed` + `setprecision(N)` configura o `cout` para imprimir sempre `N` casas decimais em notação fixa. Sem isso, problemas com `double` podem gerar **WA** por diferença de arredondamento na saída.

`10` casas decimais é o suficiente para a maioria dos problemas.

</div>

</Transition>
</div>

</div>

<style>
.fade-enter-active, .fade-leave-active { transition: opacity 0.5s ease; }
.fade-enter-from, .fade-leave-to { opacity: 0; }
</style>
