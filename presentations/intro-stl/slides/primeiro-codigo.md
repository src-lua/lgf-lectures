---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Primeiro código

Vamos começar a montar o nosso template de programação competitiva a partir do código mais básico em qualquer linguagem: Um "Hello World"!

&nbsp;

```cpp {all|1-2|5-6|8|10}
#include <iostream>
#include <string>

int main() {
    std::string name;
    std::cin >> name;
    
    std::cout << "Hello, " << name << "!" << std::endl;

    return 0;
}
```

::right::

O código é formado por 4 estruturas principais:

1. **Bibliotecas (Includes):** Importamos as ferramentas do C++.
2. **Declaração e Leitura:** Criamos o espaço na memória `std::string name;` e capturamos a entrada enviada pelo juiz online usando `std::cin`.
3. **Saída (Output):** Imprimimos a resposta no formato exato exigido usando `std::cout`.
4. **Retorno de Sucesso:** O `return 0;` avisa ao sistema (e ao juiz) que o programa terminou sem erros.