---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Complexidade Espacial

Assim como o tempo, a **memória é um recurso limitado**. Em CP, o limite típico é 256–512 MB — estourá-lo gera **MLE** (*Memory Limit Exceeded*).

**Complexidade de Espaço** mede quanta memória o programa utiliza em função de $N$.

Para calcular a memória de uma estrutura, basta multiplicar o número de elementos pelo tamanho do tipo.

**Exemplo:** um array de $10^6$ `int`s usa:

$$10^6 \times 4\,\text{bytes} = 4\,\text{MB}$$

Cabe confortavelmente em 256 MB. O mesmo array com `long long` usa o dobro: **8 MB**.

::right::

Escolher o tipo de dado correto é o primeiro passo para controlar o uso de memória. Cada tipo tem um tamanho fixo e um intervalo de valores que define quando deve ser usado.

**Tipos mais usados em CP:**

- `int` — uso geral; suficiente para $|a| \leq 2 \times 10^9$
- `long long` — quando o resultado pode ultrapassar $2 \times 10^9$
- `double` — respostas com casas decimais (~15 dígitos de precisão)
- `char` — processamento de caracteres e strings
- `bool` — arrays de flags e estado binário
