---
layout: two-cols
---

<LogoBar variant="black" position="header" align="right" />

# Anatomia de um problema

Ao submeter seu código, a plataforma vai testá-lo contra vários "casos de teste". Estes são os principais vereditos:

- **AC (Accepted):** O tão sonhado verde! Código correto e dentro do tempo.
- **WA (Wrong Answer):** Lógica incorreta, erro de formatação na saída ou algum caso de borda esquecido.
- **TLE (Time Limit Exceeded):** Código muito lento. Precisa otimizar.
- **RE (Runtime Error):** O programa "quebrou" (ex.: segfault, crash).
- **CE (Compile Error):** Erro de sintaxe (ex.: faltou um ponto e vírgula).

::right::

Todo problema é formado por 4 seções principais que exigem atenção:

- **TL / ML (Limites):** *Time Limit* e *Memory Limit*: as restrições de eficiência do seu código.
- **Statement (Descrição):** A historinha ou formulação matemática do que deve ser feito.
- **Input (Entrada):** O formato dos dados e os ***limites das variáveis*** (ex.: 1 ≤ N ≤ 10⁵). Crucial para prever a complexidade do algoritmo e evitar vazamento de memória.
- **Output (Saída):** O formato exato e rígido da resposta esperada. O juiz é cego: um espaço extra ou falta de quebra de linha pode gerar um veredito de WA.

