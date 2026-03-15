---
layout: default
---

<LogoBar variant="black" position="header" align="right" />

# Complexidade Espacial

<div class="ct-wrap">
<table class="ct">
<thead>
<tr>
  <th>Tipo</th>
  <th>O que armazena</th>
  <th>Tamanho</th>
  <th>Intervalo de Valores</th>
</tr>
</thead>
<tbody>
<tr>
  <td>int</td>
  <td>Inteiro</td>
  <td>4 bytes</td>
  <td>≈ ±2×10<sup>9</sup></td>
</tr>
<tr>
  <td>long long (ll)</td>
  <td>Inteiro 64-bit</td>
  <td>8 bytes</td>
  <td>≈ ±9×10<sup>18</sup></td>
</tr>
<tr>
  <td>char</td>
  <td>Caractere</td>
  <td>1 byte</td>
  <td>ASCII (0–127)</td>
</tr>
<tr>
  <td>bool</td>
  <td>Booleano</td>
  <td>1 byte</td>
  <td>true / false</td>
</tr>
<tr>
  <td>float</td>
  <td>Real precisão simples</td>
  <td>4 bytes</td>
  <td>~7 dígitos decimais</td>
</tr>
<tr>
  <td>double</td>
  <td>Real precisão dupla</td>
  <td>8 bytes</td>
  <td>~15 dígitos decimais</td>
</tr>
<tr>
  <td>long double</td>
  <td>Real precisão estendida</td>
  <td>16 bytes</td>
  <td>~18–19 dígitos decimais</td>
</tr>
</tbody>
</table>
<div class="ct-legend">
  <span class="legend-note">Cada tipo de dado armazena um tipo diferente de informação e ocupa uma quantidade específica de memória.</span>
</div>
</div>

<style>
.ct-wrap {
  position: absolute;
  inset: 3.5rem 2rem 1rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 0.6rem;
}
.ct {
  width: 100%;
  border-collapse: collapse;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
}
.ct th, .ct td {
  padding: 0.5em 0.9em;
  border: 1px solid #e2e8f0;
  white-space: nowrap;
}
.ct thead th {
  background: #f3f4f6;
  font-weight: 600;
  text-align: center;
}
.ct td:first-child {
  font-weight: 700;
  color: var(--primary);
}
.ct td:nth-child(3) { text-align: center; }
.ct td:nth-child(4) { text-align: right; }
.ct-legend {
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.62rem;
}
.legend-note { color: #6b7280; }
</style>
