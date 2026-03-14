# lgf-lectures

Framework para criação de apresentações técnicas com [Slidev](https://sli.dev), suporte nativo a diagramas TikZ animados e componentes Vue compartilhados entre múltiplas apresentações.

## Funcionalidades

- **TikZ build-time** — blocos TikZ compilados com `tectonic` + `dvisvgm`, com cache por SHA-256
- **`tikz-steps`** — sintaxe declarativa para animações step-by-step em diagramas TikZ sem duplicação de código
- **Componentes Vue globais** — LogoBar, Author, Copyright, FinalSlide, AnnotationBox, Counter
- **Estilos compartilhados** — base CSS e macros TikZ usados por todas as apresentações
- **Scripts de scaffold** — criação de novas apresentações e slides com um comando

## Pré-requisitos

- [Node.js](https://nodejs.org) 18+
- [tectonic](https://tectonic-typesetting.github.io) — engine LaTeX (substitui o TeX Live)
- [dvisvgm](https://dvisvgm.de) — converte PDF para SVG

```bash
# macOS
brew install tectonic dvisvgm
```

## Estrutura do repositório

```
lgf-lectures/
├── shared/
│   ├── components/          # Vue: TikzMorph, LogoBar, Author, Copyright, FinalSlide, AnnotationBox, Counter
│   ├── layouts/             # Layouts Slidev: code-compare, diagram
│   ├── styles/
│   │   ├── base.css         # CSS principal (importado por todas as apresentações)
│   │   └── fonts.css        # Google Fonts
│   ├── public/              # Assets estáticos: logos, images, backgrounds
│   ├── tikz-macros/
│   │   └── common.tex       # Estilos TikZ compartilhados
│   ├── vite-plugin-tikz.ts  # Plugin Vite para compilação de blocos TikZ
│   └── setup/
│       └── main.ts          # Template de registro de componentes
├── presentations/
│   └── seg-tree/            # Exemplo: "Variações de Segment Tree"
├── scripts/
│   ├── new-pres.sh          # Scaffold de nova apresentação
│   └── new-slide.sh         # Adiciona slide a uma apresentação existente
└── _archive/                # Conteúdo original arquivado
```

## Rodando uma apresentação

```bash
cd presentations/seg-tree
npm install
npm run dev
```

Outros comandos disponíveis:

```bash
npm run build         # Build estático
npm run export        # Exportar para HTML (com clicks)
npm run export-pdf    # Exportar para PDF
npm run export-png    # Exportar para PNG (por slide)
```

## Criando uma nova apresentação

```bash
./scripts/new-pres.sh <nome> "<Título>" "<Subtítulo>"

# Exemplo
./scripts/new-pres.sh grafos "Grafos" "BFS, DFS, Dijkstra"
```

Isso cria `presentations/grafos/` com toda a estrutura necessária (package.json, vite.config.ts, setup, styles, slides/intro.md).

Depois:

```bash
cd presentations/grafos
npm install
npm run dev
```

## Adicionando slides

```bash
./scripts/new-slide.sh <apresentação> <nome> [tipo]
```

Tipos disponíveis:

| Tipo | Descrição |
|------|-----------|
| `default` | Slide de conteúdo padrão |
| `section` | Divisor de seção |
| `two-cols` | Layout em duas colunas |
| `tikz-steps` | Diagrama TikZ animado (recomendado) |
| `tikz` | TikzMorph manual com templates explícitos |
| `code` | Comparação de código com magic-move |

```bash
# Exemplos
./scripts/new-slide.sh seg-tree complexidade default
./scripts/new-slide.sh grafos bfs-walk tikz-steps
```

O slide é criado em `slides/<nome>.md` e a referência `src:` é inserida automaticamente no `slides.md`.

## Sintaxe tikz-steps

A principal feature do projeto: blocos TikZ animados sem repetição de código.

````md
```tikz-steps{scale=1.3}
\begin{tikzpicture}[...]
  \node[{{root}}] {22}
    child { node[{{L}}] {5} }
    child { node[{{R}}] {22} };
\end{tikzpicture}
---0---

---1---
root: pathnode
---2---
root: pathnode
L: reject
R: target
```
````

- `{{placeholder}}` — slot de estilo substituído por step
- `---N---` seguido de YAML — overrides do step N
- O plugin compila N SVGs e emite `<TikzMorph>` automaticamente
- `clicks: N` é injetado no frontmatter se não declarado

## Estilos TikZ disponíveis

Definidos em [shared/tikz-macros/common.tex](shared/tikz-macros/common.tex):

| Estilo | Visual |
|--------|--------|
| `pathnode` | laranja — nó no caminho ativo |
| `reject` / `pruned` | vermelho tracejado — ramo podado |
| `target` | verde duplo — objetivo encontrado |
| `active` | laranja — sendo processado |
| `done` | verde — processado |
| `highlight` | amarelo — enfatizado |
| `common` | amarelo escuro — compartilhado |
| `deadend` | roxo — beco sem saída |
| `newnode` | vermelho claro — nó novo |
| `shared` | azul — compartilhado |
| `voidnode` | cinza transparente — vazio |

## Componentes Vue

Todos os componentes são registrados globalmente em cada apresentação.

### `<LogoBar>`

```vue
<LogoBar variant="black|white|pb" position="header|footer" align="default|right" />
```

### `<Author>`

```vue
<Author :authors="['Nome Completo <tag>']" />
```

### `<Copyright>`

```vue
<Copyright version="rev. 1.0" />
```

### `<AnnotationBox>`

```vue
<AnnotationBox size="normal|small">Texto da anotação</AnnotationBox>
```

### `<Counter>`

```vue
<Counter :count="0" />
```

### `<FinalSlide>`

```vue
<FinalSlide />
```

### `<TikzMorph>`

Usado internamente pelo plugin `tikz-steps`. Para uso manual:

```vue
<TikzMorph>
  <template #0><!-- SVG/TikZ step 0 --></template>
  <template #1><!-- SVG/TikZ step 1 --></template>
</TikzMorph>
```

## Cache TikZ

Os SVGs compilados ficam em `.tikz-cache/` dentro de cada apresentação, indexados por SHA-256 do conteúdo. O diretório é ignorado pelo git.
