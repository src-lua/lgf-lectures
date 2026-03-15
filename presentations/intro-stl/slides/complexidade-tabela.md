---
layout: default
---

<LogoBar variant="black" position="header" align="right" />

# Complexidade Temporal e Espacial

<div class="ct-wrap">
<table class="ct">
<thead>
<tr>
  <th>Complexidade</th>
  <th>N máx. (≈1s)</th>
  <th>N = 10</th>
  <th>N = 100</th>
  <th>N = 10<sup>3</sup></th>
  <th>N = 10<sup>4</sup></th>
  <th>N = 10<sup>5</sup></th>
  <th>N = 10<sup>6</sup></th>
</tr>
</thead>
<tbody>
<tr>
  <td>O(log N)</td>
  <td class="nmax">≈ 10<sup>10</sup></td>
  <td class="ok">~3</td><td class="ok">~7</td><td class="ok">~10</td><td class="ok">~13</td><td class="ok">~17</td><td class="ok">~20</td>
</tr>
<tr>
  <td>O(N)</td>
  <td class="nmax">≈ 10<sup>8</sup></td>
  <td class="ok">10</td><td class="ok">100</td><td class="ok">1.000</td><td class="ok">10.000</td><td class="ok">100.000</td><td class="ok">1.000.000</td>
</tr>
<tr>
  <td>O(N log N)</td>
  <td class="nmax">≈ 10<sup>6</sup></td>
  <td class="ok">~33</td><td class="ok">~664</td><td class="ok">~9.965</td><td class="ok">~132.877</td><td class="ok">~1.661.000</td><td class="ok">~19.932.000</td>
</tr>
<tr>
  <td>O(N<sup>2</sup>)</td>
  <td class="nmax">≈ 10<sup>4</sup></td>
  <td class="ok">100</td><td class="ok">10.000</td><td class="ok">10<sup>6</sup></td><td class="ok">10<sup>8</sup></td><td class="tle">10<sup>10</sup></td><td class="tle">10<sup>12</sup></td>
</tr>
<tr>
  <td>O(N<sup>3</sup>)</td>
  <td class="nmax">≈ 4×10<sup>2</sup></td>
  <td class="ok">1.000</td><td class="ok">10<sup>6</sup></td><td class="tle">10<sup>9</sup></td><td class="tle">10<sup>12</sup></td><td class="tle">10<sup>15</sup></td><td class="tle">10<sup>18</sup></td>
</tr>
<tr>
  <td>O(2<sup>N</sup>)</td>
  <td class="nmax">≈ 26</td>
  <td class="ok">1.024</td><td class="tle">≈ 10<sup>30</sup></td><td class="tle">∞</td><td class="tle">∞</td><td class="tle">∞</td><td class="tle">∞</td>
</tr>
<tr>
  <td>O(N!)</td>
  <td class="nmax">≈ 11</td>
  <td class="ok">3.628.800</td><td class="tle">≈ 10<sup>157</sup></td><td class="tle">∞</td><td class="tle">∞</td><td class="tle">∞</td><td class="tle">∞</td>
</tr>
</tbody>
</table>
<div class="ct-legend">
  <span class="legend-ok">Dentro do limite</span>
  <span class="legend-tle">Provável TLE</span>
  <span class="legend-note">Valores em número de operações. Assumindo ≈ 10<sup>8</sup> ops/s no juiz.</span>
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
  font-size: 0.68rem;
}
.ct th, .ct td {
  padding: 0.45em 0.7em;
  border: 1px solid #e2e8f0;
  text-align: right;
  white-space: nowrap;
}
.ct thead th {
  background: #f3f4f6;
  font-weight: 600;
  text-align: center;
}
.ct td:first-child {
  text-align: left;
  font-weight: 700;
  color: var(--primary);
}
.ct td.nmax {
  text-align: center;
  color: #6b7280;
  font-style: italic;
}
.ct td.ok {
  background: #16a34a;
  color: white;
  font-weight: 600;
}
.ct td.tle {
  background: var(--primary);
  color: white;
  font-weight: 600;
  text-align: center;
}
.ct-legend {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.62rem;
}
.legend-ok, .legend-tle {
  padding: 0.2em 0.7em;
  border-radius: 4px;
  color: white;
  font-weight: 600;
}
.legend-ok  { background: #16a34a; }
.legend-tle { background: var(--primary); }
.legend-note { color: #6b7280; margin-left: auto; }
</style>
