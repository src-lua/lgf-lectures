---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Complexidade Temporal e Espacial

Em competições, não basta ter um código que funciona — ele precisa ser rápido o suficiente para rodar dentro do tempo limite (1–2s). A análise de complexidade nos ajuda a **prever a velocidade de um algoritmo** sem precisar executá-lo.

**Regra prática:** CPUs modernas executam cerca de $10^8$ operações por segundo. Se sua complexidade ultrapassa esse limite para o $N$ do problema, o veredicto provavelmente será **TLE**.

A **notação Big O** descreve como o tempo de execução cresce conforme $N$ aumenta. Focamos no **pior caso** e ignoramos constantes e termos de menor ordem.

**Exemplo:** $3N^2 + 5N + 10 \;\Rightarrow\; O(N^2)$

::right::

**Complexidades comuns em CP:**

- $\boldsymbol{O(1)}$: acesso a array, operação aritmética
- $\boldsymbol{O(\log N)}$: busca binária, operações em heap
- $\boldsymbol{O(N)}$: loop simples, leitura do input
- $\boldsymbol{O(N \log N)}$: ordenação (`std::sort`)
- $\boldsymbol{O(N^2)}$: dois loops aninhados, força bruta simples
- $\boldsymbol{O(2^N)}$: geração de todos os subconjuntos
- $\boldsymbol{O(N!)}$: geração de todas as permutações
